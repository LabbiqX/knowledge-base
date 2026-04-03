---
layout: summary
title: "Harness Engineering: Uzun Süreli Otonom Agent Sistemleri Tasarımı"
date: 2026-03-18
source: "https://www.youtube.com/watch?v=kJPvfoLtFFY"
category: "AI Agent Architecture"
type: "Makale"
---

## TL;DR
Aralık 2025'ten itibaren modeller uzun süreli otonom görevlere hazır hale geldi — paradigma co-pilot'tan **always-on otonom agent'lara** kayıyor. Bunun kilidi "harness engineering": agent'ın çalışacağı ortamı **okunabilir (legible)** tasarla, **doğrulama (verification)** döngüsü kur, ve modele güven — özel araçlar yerine **jenerik, model-native araçlar** ver. Basit mimari + iyi bağlam ortamı = daha iyi sonuç.

---

## Paradigma Değişimi: Co-pilot → Otonom Agent
- Aralık 2025'te modeller uzun süreli tutarlılık ve karmaşık görev kapasitesinde sıçrama yaptı
- AutoGPT (2023) aynı hayali kuruyordu ama modeller hazır değildi — şimdi hazır
- Cursor GPT-5.2 ile sıfırdan 3M satır kodla tarayıcı üretti
- Anthropic, Claude Code ekibiyle 2 haftada sıfırdan C derleyicisi üretti (Doom çalıştırabilen)
- OpenClaw bu trendin sembolü: always-on, proaktif, tam bilgisayar erişimli otonom agent

## Harness Engineering Nedir?
Prompt engineering → Context engineering → **Harness engineering** evrimi:
- Prompt eng: tek prompt optimizasyonu
- Context eng: efektif context window içinde bilgi optimizasyonu
- **Harness eng:** Oturumlar arası, çoklu agent, uzun süreli görevlerde **ortam + iş akışı + araç tasarımı**

## 3 Temel İlke

### 1. Okunabilir Ortam (Legible Environment)
Agent yeni bir oturum başlattığında durumu hızlıca kavrayabilmeli.

**Anthropic yaklaşımı:**
- **Initializer agent** → ortamı kurar (dev server, init script, progress dosyası, git commit)
- **Feature list** → 200+ özellik JSON'da tanımlı, hepsi varsayılan "fail" — agent one-shot yapmak yerine sırayla çalışır
- Her oturum sonunda: git commit + progress dosyası güncelle → temiz ortam bırak

**OpenAI yaklaşımı:**
- Dev AGENTS.md yerine **içindekiler tablosu** yapısı — progressive disclosure
- Mimari dokümanları, tasarım kararları, DB şema, ürün spec'leri ayrı dosyalarda
- Google Doc, Slack mesajları bile repo'ya lokal artifact olarak çekildi
- Agent açısından: **ortamda erişilemiyorsa, yok demektir**

### 2. Doğrulama Kritik (Verification & Fast Feedback Loop)
- Model varsayılan olarak "tamamlandı" diye işaretler ama gerçekte çalışmaz
- Unit test / API test yeterli değil — **uçtan uca test** şart
- Puppeteer MCP veya Chrome DevTools vererek agent'ın kendi işini **kendisi test etmesi** sağlandı
- Git pre-commit hook'ları ile mimari kurallar, linter'lar, yapısal testler otomatik tetikleniyor
- Codex iş akışı: durumu doğrula → bug'ı reproduce et → video kaydet → düzelt → fix'i doğrula → ikinci video → merge

### 3. Modele Güven, Jenerik Araçlar Ver
- Özel araçlar (specialized tooling) kırılgan, yavaş, sürekli bakım gerektirir
- Vercel deneyimi: sofistike text-to-SQL agent'ı sadeleştirip **tek bash komutu** aracına indirdi → **3.5x hızlı, %37 daha az token, başarı %80→%100**
- Anthropic: search/lint/execute yerine tek bash aracı (grep, npm, lint hepsi bash'ten)
- Modeller milyarlarca token'lık eğitimle code-native araçları (bash, grep, git) zaten biliyor — bespoke JSON tool calling'den çok daha iyi performans
- **OpenClaw felsefesi:** read, write, edit, bash, send message — temel araçlar + skill kütüphanesi ile genişleme

---

## 🎯 Anahtar Çıkarım
> Modeller zaten güçlü — darboğaz modelin zekası değil, **çalışacağı ortamın tasarımı.** Okunabilir ortam + doğrulama döngüsü + jenerik araçlara güven = uzun süreli otonom agent başarısı. Özel araçlar yerine basit mimari + iyi bağlam her zaman kazanıyor.
