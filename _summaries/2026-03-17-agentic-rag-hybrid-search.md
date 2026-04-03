---
layout: summary
title: "How to Build Agentic RAG with Hybrid Search"
date: 2026-03-17
source: "https://towardsdatascience.com/how-to-build-agentic-rag-with-hybrid-search/"
category: "RAG & Knowledge"
type: "Makale"
---

## TL;DR
Klasik RAG'ın vector-only araması anahtar kelime ve ID aramalarında yetersiz kalır. **Hybrid search** (vector + BM25 keyword) bunu çözer. Asıl güç: arama fonksiyonunu LLM'e **tool olarak** vererek agentic yapmak — agent query rewriting, iteratif getirme ve dinamik ağırlıklama yaparak statik RAG'ı ciddi şekilde geride bırakır.

---

## Problem
Klasik RAG sadece **vector similarity** kullanır. Semantik benzerlik için güçlüdür ama **belirli anahtar kelimeler veya ID'ler** arandığında yetersiz kalır — vektör araması tek bir kelimeye yüksek ağırlık vermez, o kelime diğer kelimelerin arasında kaybolur.

## Çözüm: Hybrid Search
**Vector similarity + Keyword search (BM25)** birleşimi:

- **Vector search:** Anlamsal benzerlik, eşanlamlılar, yazım hataları — bunlarda güçlü
- **BM25 keyword search:** Belirli kelime veya ID'ler — bunlarda güçlü. Bir kelime sadece tek dokümanda geçiyorsa, o doküman çok yüksek ağırlık alır
- İkisi arasında bir **ağırlık (weighting)** belirlenir

## Asıl Güç: Agentic Yapı
Klasik RAG: chunk getir → LLM'e ver → cevap.
**Agentic RAG:** Chunk getirme fonksiyonunu LLM'e **tool olarak** ver. 3 kritik avantaj:

1. **Query Rewriting** — Agent kullanıcının prompt'unu yeniden yazarak daha iyi arama sonuçları alabilir
2. **İteratif Getirme** — İlk aramada yeterli bilgi yoksa agent tekrar arama yapabilir, bilgiyi değerlendirir ve eksikse tamamlar
3. **Dinamik Ağırlıklama** — Agent, keyword mi yoksa semantik arama mı daha önemli karar verir. Statik ağırlıktan çok daha etkili

---

## 🎯 Anahtar Çıkarım
> Hybrid search + agentic yapı birleşimi, statik vector-only RAG'a kıyasla ciddi performans artışı sağlıyor. Bugünün frontier LLM'leri query rewriting, iteratif getirme ve dinamik ağırlıklama kararlarını kendi başına verebilecek kadar güçlü.
