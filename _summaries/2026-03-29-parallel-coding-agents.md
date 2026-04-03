---
layout: summary
title: "How to Run Coding Agents in Parallel"
date: 2026-03-29
source: "https://towardsdatascience.com/how-to-run-coding-agents-in-parallell/"
category: "AI Coding Tools"
type: "Makale"
---

## TL;DR
Boris Cherny (Claude Code yaratıcısı) aynı anda 10-20 agent çalıştırıyor. Framework: öncelikli görev listesi tut → plan mode ile detaylı talimat ver (20dk harcamaktan korkma) → agent'ı başlat → sıradaki göreve geç → ilk agent geri geldiğinde döngüye devam. CLI araçları (Claude Code + Warp terminal) paralel çalışma için en uygun.

---

## 4 Adımlı Framework
1. En yüksek etkili görevi bul
2. Plan mode'da Claude ile çözümü tartış (15-20dk, edge case'ler dahil)
3. Agent'ı ateşle, ikinci göreve geç
4. İlk agent feedback istediğinde yeni agent başlatmayı durdur

## 3 Gereksinim
- **Öncelikli görev listesi:** Value-effort grafiği, Todoist/Notion ile yönetim
- **Plan mode:** Belirsiz talimat çalışmaz — detaylı plan = daha az hata = daha az iterasyon
- **CLI aracı:** Cursor paralel çalışmada zayıf → Claude Code + Warp terminal (CMD+D ile pane bölme)

## Önemli Tavsiyeler
- Ucuz model = daha fazla hata = daha fazla iterasyon = sonuçta daha pahalı
- Plan mode'da harcanan 20dk sonradan katlanarak geri dönüyor
- Context switching hala minimize edilmeli — ama agent çalışırken bekleme değersiz

---

## 🎯 Anahtar Çıkarım
> Paralel agent çalıştırmak yeni "default" çalışma biçimi. En kritik adım: iyi plan + detaylı talimat. "Vague instruction + spin up" çalışmıyor — 20dk plan mode yatırımı her zaman geri dönüyor.
