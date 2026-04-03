---
layout: summary
title: "GraphRAG in Practice: Cost-Efficient, High-Recall Retrieval"
date: 2026-03-29
source: "https://towardsdatascience.com/graphrag-in-practice-how-to-build-cost-efficient-high-recall-retrieval-systems/"
category: "RAG & Knowledge"
type: "Makale"
---

## TL;DR
Tam bir graph (tüm entity+relation) oluşturmak ölçekte çok pahalı. Pratik çözüm: minimal star graph (ReportId→Entity, HAS_ENTITY ilişkisi) + iterative search-space optimization ile ilişkileri çıkarım zamanında keşfet. Chunked extraction 3x daha fazla entity buluyor ama maliyet artıyor. Graph'ın asıl değeri: doküman filtreleme (doc_id sınıflandırıcı), zayıf embedding'leri düzeltme (alfanümerik ID'ler), sorgu zenginleştirme.

---

## Pipeline
1. **Embedding:** Dokümanlardan entity çıkar → Neo4j'ye yaz + chunk embedding'leri
2. **Retrieval:** Graph sonucu direkt yanıt değil → doküman filtresi + query enrichment
3. **Generation:** Filtrelenmiş chunk'larla LLM yanıt üretir

## Graph Oluşturma: Chunk vs Full Document
| Yaklaşım | Entity Sayısı | Maliyet |
|-----------|---------------|---------|
| Full document | ~22 node | Düşük |
| Chunked (2000 char) | ~78 node (3x) | Yüksek |

- Uzun dokümanlar → LLM attention dilution → entity kaçırma
- Chunking çözer ama iterasyon maliyeti artar

## Graph'ın Değer Kattığı Yerler
- **Doc_id sınıflandırma:** Büyük corpus'ta naive vector similarity gürültülü → graph entity ile doküman filtrele
- **Zayıf embedding düzeltme:** Alfanümerik ID'ler (plaka, rapor no) vector search'te çalışmaz → graph context
- **İteratif arama:** Önce doküman seç, sonra chunk seç — iki aşamalı daraltma

## Minimal Graph Yeterli mi?
- Star graph + HAS_ENTITY yeterli olabilir — ilişkileri graph'a yazmadan da çıkarılabilir
- İteratif retrieval pipeline ile sparse graph'tan bile relation soruları yanıtlanabilir
- Prominent entity referansı ile soru yönlendirme: "Ravi Sharma hangi raporlarda?" yerine "Mumbai raporlarından hangilerinde Ravi Sharma var?"

---

## 🎯 Anahtar Çıkarım
> GraphRAG'ın gerçek gücü "her şeyi graph'a yaz" değil, "graph'ı akıllı filtre olarak kullan." Minimal star graph + iteratif search-space optimization, tam dense graph'ın çoğu faydasını çok daha düşük maliyetle sağlıyor.
