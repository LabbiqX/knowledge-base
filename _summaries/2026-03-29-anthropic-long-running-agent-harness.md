---
layout: summary
title: "Effective Harnesses for Long-Running Agents"
date: 2026-03-29
source: "https://www.anthropic.com/engineering/effective-harnesses-for-long-running-agents"
category: "AI Agent Architecture"
type: "Makale"
---

## TL;DR
Uzun süreli çalışan agent'ların temel sorunu: her yeni context window sıfırdan başlıyor, önceki session'ın hafızası yok. Anthropic'in çözümü iki parça: (1) Initializer agent — ortamı hazırlayan, feature listesi ve init script oluşturan ilk session, (2) Coding agent — her session'da tek feature üzerinde artırımlı ilerleme yapan, git commit + progress dosyası bırakan agent. Anahtar: claude-progress.txt + git history = agent'ın hızla durum kavraması.

---

## Problem
- Context window sınırlı → karmaşık projeler tek window'da bitmez
- Compaction yeterli değil — sonraki session'a net talimat geçiremiyor
- **Başarısızlık modu 1:** Agent her şeyi tek seferde yapmaya çalışır → context ortasında tükenir → yarım kalmış, belgelenmemiş kod
- **Başarısızlık modu 2:** Sonraki agent ilerlenmiş projeyi görür → "iş bitti" der → erken zafer ilanı

## İki Parçalı Çözüm

### 1. Initializer Agent (İlk Session)
- **Feature listesi:** Kullanıcının prompt'undan kapsamlı özellik listesi çıkarır (claude.ai klonunda 200+ feature)
- Tüm feature'lar başlangıçta "failing" — net hedef
- JSON formatı tercih (Markdown'dan daha az overwrite riski)
- **init.sh script:** Dev server başlatma, temel test çalıştırma
- **İlk git commit:** Başlangıç durumunu belgele

### 2. Coding Agent (Sonraki Session'lar)
Her session şu akışı izler:
1. `pwd` → çalışma dizini
2. `claude-progress.txt` oku → son durum
3. `feature_list.json` oku → sıradaki feature
4. `git log --oneline -20` → son değişiklikler
5. init.sh çalıştır → dev server başlat
6. Temel test → mevcut işlevsellik kontrol
7. **Tek feature üzerinde çalış**
8. End-to-end test (browser automation — Puppeteer MCP)
9. Git commit + progress güncelle

## Kritik Tasarım Kararları
- **Artırımlı ilerleme:** Tek seferde tüm uygulamayı değil, tek feature'ı tamamla
- **Temiz state bırak:** Her session sonrası merge-ready kod — bug yok, belgelenmiş, düzenli
- **Git = geri alma mekanizması:** Kötü değişiklikleri revert edebilme
- **Browser automation testi:** Kod testleri yetmez, kullanıcı gibi end-to-end test şart
- **JSON > Markdown:** Feature listesi için — model JSON'u daha az bozuyor

## Sorun-Çözüm Tablosu
| Sorun | Initializer | Coding Agent |
|-------|------------|--------------|
| Erken zafer ilanı | Feature list oluştur | Feature list oku, tek feature seç |
| Buglu/belgelenmemiş bırakma | Git repo + progress dosyası | Session başında oku, sonunda güncelle |
| Feature'ı test etmeden tamamlandı sayma | Feature list kur | Self-verify, sadece test sonrası "passing" |
| Uygulamayı nasıl çalıştıracağını bilmeme | init.sh yaz | init.sh oku, server başlat |

## Açık Sorular
- Tek genel amaçlı agent mı, yoksa uzmanlaşmış multi-agent (test, QA, cleanup) mı daha iyi?
- Web app dışı alanlara (bilimsel araştırma, finansal modelleme) genellenebilir mi?

---

## 🎯 Anahtar Çıkarım
> Uzun süreli agent'ların çalışması için "vardiya değişimi" metaforu geçerli: her yeni mühendis öncekinin notlarını okumalı. Feature listesi (JSON) + progress dosyası + git history üçlüsü, agent'ın hızla durumu kavramasını sağlıyor. En kritik kural: tek seferde tek feature, temiz state bırak.
