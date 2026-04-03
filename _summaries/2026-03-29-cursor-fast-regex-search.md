---
layout: summary
title: "Fast Regex Search: Indexing Text for Agent Tools"
date: 2026-03-29
source: "https://cursor.com/blog/fast-regex-search"
category: "AI Agent Architecture"
type: "Makale"
---

## TL;DR
Cursor, agentic coding'de ripgrep'in büyük monorepo'larda 15+ saniye sürmesi sorununu çözmek için trigram tabanlı inverted index sistemi geliştirdi. 1973'ten gelen grep → LSP → tekrar grep döngüsü, agent'ların doğası gereği regex aramayı sevmesinden kaynaklanıyor. Trigram decomposition ile regex pattern'leri indekslenerek aday dosya listesi daraltılıyor, sonra sadece bu dosyalarda geleneksel eşleştirme yapılıyor.

---

## Key Points
- Agent'lar grep/ripgrep'i yoğun kullanıyor — semantik index'ler her sorgu için yeterli değil
- Büyük monorepo'larda rg 15+ saniye sürebiliyor, bu agent akışını durdurma sorunu
- **Trigram indeksleme:** Her 3 karakterlik örtüşen segment bir token; inverted index ile posting list'lere map'leniyor
- Bigram: çok az key, çok büyük posting list'ler / Quadgram: çok fazla key → trigram optimal denge
- Regex pattern'leri parse edilip trigram'lara decompose ediliyor: literal string, alternation, character class desteği
- Sonuç: potansiyel dosya listesi daraltılıyor, ardından gerçek regex eşleştirme sadece aday dosyalarda yapılıyor
- 1993'teki Zobel et al. paper'ına dayanan yaklaşım; Russ Cox'un 2012 Google Code Search blog post'u ile popülerleşti

---

## 🎯 Anahtar Çıkarım
> Agentic coding, arama teknolojisini 1973'e geri götürdü ama trigram indeksleme ile grep'i IDE seviyesinde hızlandırmak mümkün — agent araçları için inverted index, semantic search kadar kritik bir altyapı katmanı.
