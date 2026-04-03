---
layout: summary
title: "DeepSeek's Conditional Memory (Engram)"
date: 2026-03-29
source: "https://venturebeat.com/data/deepseeks-conditional-memory-fixes-silent-llm-waste-gpu-cycles-lost-to"
category: "RAG & Knowledge"
type: "Makale"
---

## TL;DR
DeepSeek'in Engram modülü statik bilgi aramayı (entity isimleri, teknik terimler) dinamik akıl yürütmeden ayırıyor. Transformer'lar şu an "telefon numarasını hatırlamak için hesap makinesi kullanıyor." Optimum ayrım: %75 hesaplama, %25 hafıza. Reasoning benchmark'ları %70→74, knowledge testleri %57→61. 100B parametre CPU RAM'e offload, throughput kaybı <%3. GPU bellek maliyetinde potansiyel paradigma değişimi.

---

## Problem
- LLM statik bilgi araması (entity, terim, kloz) için pahalı GPU hesaplama kullanıyor
- "Diana, Princess of Wales" tanımak için katmanlar arası attention + FFN gerekiyor
- O(1) olması gereken lookup O(n) hesaplama ile simüle ediliyor

## Çözüm: Engram
- 2-3 token dizisi → hash fonksiyonu → büyük embedding tablosu → sabit zamanda retrieval
- **Gating mekanizması:** Bağlam filtresi — "Apple" elma mı şirket mi? Önceki attention katmanlarından gelen context karar veriyor
- Stratejik katman yerleşimi — her katmanda değil

## Agentic Memory vs Conditional Memory
| | Agentic (Hindsight, MemOS) | Conditional (Engram) |
|---|---|---|
| **Ne çözer** | Geçmiş konuşma, tercihler, episodik hafıza | Statik pattern arama verimliliği |
| **Nerede** | Model dışı, harici | Model içi, forward pass |
| **Hedef** | Oturum arası bağlam | GPU verimlilik, küçük model performansı |

## Optimum Ayrım: %75/%25
- %75 sparse kapasite → dinamik reasoning
- %25 → statik lookup hafıza
- Saf MoE (%100 hesaplama) suboptimal — depth statik pattern'ları yeniden oluşturmakla harcanıyor

## Altyapı İnovasyonu
- 100B parametre embedding tablosu → CPU DRAM'e offload
- GPU hesaplama sırasında PCIe üzerinden asenkron retrieval
- Throughput kaybı <%3
- Erken katman hesaplaması = iletişim latency'sini maskeleyen buffer

## Kurumsal Etkiler
- Hibrit mimari > saf yaklaşım
- Yatırım kayması: GPU → memory-rich konfigürasyonlar
- Sürpriz: hafıza iyileştirmesi reasoning'e knowledge'dan daha çok fayda sağlıyor

---

## 🎯 Anahtar Çıkarım
> Conditional memory "model içi" bir optimizasyon — agentic memory'nin tersi. Statik bilgi aramayı O(1)'e indirerek GPU döngülerini gerçek reasoning için serbest bırakıyor. %75/25 kuralı ve CPU offload ile kurumsal AI altyapısında maliyet yapısını değiştirebilir.
