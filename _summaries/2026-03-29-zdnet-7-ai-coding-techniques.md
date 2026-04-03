---
layout: summary
title: "7 AI Coding Tekniği: Gerçek, Güvenilir Ürünler Hızla Çıkarmak"
date: 2026-03-29
source: "https://www.zdnet.com/article/ai-coding-techniques/"
category: "AI Agent Architecture"
type: "Makale"
---

## TL;DR
Deneyimli bir geliştirici, Codex ve Claude Code ile Eylül 2025'ten bu yana 4 büyük WordPress eklentisi + iPhone/iPad/Watch/Mac uygulaması geliştirdi. 7 temel best practice paylaşıyor: sıralı çalışma (paralel değil), migration tracking, kalıcı memory, prompt logging, ve daha fazlası.

---

## Key Points
1. **Sequential visibility > parallel speed:** Paralel agent'lar crash ve hang yapıyor — tek agent sıralı çalışsın
2. **Migration tracking:** Her platform değişikliği teknik borç ticket'ı oluşturur — IOS_CHANGES_FOR_MIGRATION.md
3. **Persistent memory (MEMORY.md):** Konuya göre organize, session'lar arası kalıcı bilgi tabanı — "Don't reinvent the wheel"
4. **Prompt logging:** Her prompt audit trail olarak loglanır
5. **Design system kodlama:** UI kuralları ve kullanıcı profilleri system prompt'a yazılır
6. **Bug = kalıcı ders:** Her düzeltilen bug projenin DNA'sına yazılır
7. **AI'ı geliştirici olarak gör, sihirli kutu olarak değil**
- CLAUDE.MD ve AGENTS.MD dosyalarına tüm kurallar yazılı
- 4 yıllık geliştirmeyi 4 günde $200'a yaptı

---

## 🎯 Anahtar Çıkarım
> Vibe coding + mühendislik disiplini = production-ready ürünler — anahtar: yazılı kurallar (CLAUDE.MD), kalıcı memory, sıralı çalışma ve her bug'ı kalıcı derse dönüştürme.
