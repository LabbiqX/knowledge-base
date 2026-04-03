---
layout: summary
title: "Memory for AI Agents: A New Paradigm of Context Engineering"
date: 2026-03-29
source: "https://thenewstack.io/memory-for-ai-agents-a-new-paradigm-of-context-engineering/"
category: "RAG & Knowledge"
type: "Makale"
---

## TL;DR
AI agent hafızası yeni bir rekabet avantajı ("moat"). LLM'ler stateless — her etkileşim sıfırdan. Büyük context window yanılsaması gerçek iş yüklerinde çöktü: performans düşüşü, maliyet artışı, "context rot". İnsan hafızası gibi katmanlı sistem gerekli: working memory (RAM), short-term (geçici), long-term (kalıcı). Üç yaklaşım: vector store (retrieval), summarization (sıkıştırma), knowledge graph (yapısal bilgi).

---

## Neden Hafıza Şimdi Önemli?
- Büyük context window her şeyi çözer sanıldı → gerçek iş yüklerinde çöktü
- **Context rot/pollution:** Window büyütme = performans düşüşü
- Kısa etkileşimlerde sorun yok, günler/departmanlar arası iş akışlarında kritik
- Satış copilot'u bağlam koruduğunda araştırma süresini yarıya indirebilir
- Müşteri hizmetleri agent'ı kalıcı hafızayla churn azaltabilir

## İnsan Hafızasından Analoji
- **Working memory:** Geçici, RAM benzeri
- **Short-term memory:** Kısa süreli, kolayca bozulabilir
- **Long-term memory:** Kararlı, tekrar ve ilgi ile pekişir
- İnsan her şeyi working memory'de tutamaz → sıkıştır, soyutla, unut

## Üç Hafıza Yaklaşımı

| Yaklaşım | Nasıl | Güçlü | Zayıf |
|-----------|-------|-------|-------|
| **Vector Store** (retrieval) | Embedding + cosine similarity (Pinecone, Weaviate) | Hızlı, basit | Yüzeysel hatırlama |
| **Summarization** (sıkıştırma) | Periyodik özet, rolling summary | Kompakt | Detay kaybı |
| **Knowledge Graph** (yapısal bilgi) | Node + ilişki: kim, ne, ne zaman (Zep) | Zengin bağlam | Karmaşık setup |

## Prompt'tan Persona'ya
- 2024: Ham metin dosyalarını prompt'a geri besleme — ilkel
- Bugün: Yapılandırılmış harici veritabanları, graph-based hafıza
- Olgunlaşan altyapı: hafıza artık "hack" değil, mimari bileşen

---

## 🎯 Anahtar Çıkarım
> Agent hafızası teknik bir altyapı sorunu olduğu kadar felsefi bir netlik de gerektiriyor: ne hatırlanmalı, ne unutulmalı, ne sıkıştırılmalı? İnsan hafızasının katmanlı yapısı (working → short-term → long-term) AI agent mimarisine doğrudan uygulanabilir bir model sunuyor. Context window büyütmek çözüm değil — akıllı context management şart.
