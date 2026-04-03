---
layout: summary
title: "Hindsight: Open Source Agentic Memory — %91 Accuracy"
date: 2026-03-29
source: "https://venturebeat.com/data/with-91-accuracy-open-source-hindsight-agentic-memory-provides-20-20-vision"
category: "RAG & Knowledge"
type: "Makale"
---

## TL;DR
Vectorize.io + Virginia Tech + Washington Post'un geliştirdiği açık kaynak Hindsight, agent hafızasını dört ağa ayırıyor: dünya gerçekleri, agent deneyimleri, varlık özetleri ve evrimleşen inançlar. LongMemEval benchmark'ında %91.4 doğruluk ile en yüksek skoru aldı. RAG'in temel sorunu: tüm bilgiyi eşit işliyor, zamansallık/belirsizlik/çelişki yönetimi yok.

---

## RAG Neden Yetersiz?
- Tüm bilgiyi uniform işler — 6 aylık gerçek = dünkü görüş
- Çelişen bilgiler yan yana, uzlaştırma mekanizması yok
- Multi-session'da: ya context window'u gereksiz bilgiyle doldurur ya kritik detayları kaçırır
- Vector similarity tek başına zamansal ilişki, nedensellik zinciri çözemez

## Hindsight Mimarisi — 4 Ağ
| Ağ | İçerik | Örnek |
|----|--------|-------|
| **World** | Nesnel dış dünya gerçekleri | "Paris Fransa'nın başkenti" |
| **Bank** | Agent'ın kendi deneyimleri (1. şahıs) | "Kullanıcıya rapor gönderdim" |
| **Observation** | Tercih-nötr varlık özetleri | "Şirket X'in 500 çalışanı var" |
| **Opinion** | Öznel yargılar + güven skoru | "Bu yaklaşım etkili görünüyor (%75)" |

## İki Ana Bileşen
- **TEMPR (retrieval):** 4 paralel arama (semantic, BM25, graph traversal, temporal) → Reciprocal Rank Fusion → neural reranker
- **CARA (reasoning):** Yapılandırılabilir disposition parametreleri (skepticism, literalism, empathy) — tutarlı perspektif

## Benchmark Sonuçları (LongMemEval)
- Genel: **%91.4** (en yüksek)
- Multi-session: %21.1 → **%79.7** (3.8x artış)
- Temporal reasoning: %31.6 → **%79.7**
- Knowledge update: %60.3 → **%84.6**
- Test: 1.5M token, birden fazla session

## Kurumsal Dağıtım
- Tek Docker container, LLM wrapper ile herhangi bir modelle çalışır
- Drop-in replacement — API çağrılarını değiştir, hafıza otomatik
- Hyperscaler'larla entegrasyon çalışmaları devam ediyor

---

## 🎯 Anahtar Çıkarım
> RAG'in asıl sorunu retrieval değil, epistemik netlik eksikliği — gerçek ile çıkarım, gözlem ile inanç ayrılamıyor. Hindsight'ın 4-ağ yapısı bu ayrımı mimari düzeyde çözüyor. Multi-session doğruluğu %21→%80'e çıkması, yapısal hafızanın basit vector retrieval'ı neden geçtiğini net gösteriyor.
