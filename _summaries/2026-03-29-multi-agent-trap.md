---
layout: summary
title: "The Multi-Agent Trap"
date: 2026-03-29
source: "https://towardsdatascience.com/the-multi-agent-trap/"
category: "Multi-Agent Systems"
type: "Makale"
---

## TL;DR
Yapısız multi-agent sistemler hataları 17.2x artırır (Google DeepMind araştırması). %95 per-step güvenilirlik bile 20 adımda %35.8'e düşer. Gartner: agentic AI projelerinin %40+'ı 2027'ye kadar iptal edilecek. Ama Klarna 2.3M konuşma/ay, 700 insan eşdeğeri, %47 müşteri memnuniyeti artışı. Fark: agent sayısı değil, topoloji.

---

## Neden Daha Fazla Agent Genelde Daha Kötü?
- Google DeepMind (Yubin Kim): 180 konfigürasyon, 5 mimari, 3 LLM ailesi
- "Bag of agents" = yapısız ağ → hata amplifikasyonu 17.2x
- 4 agent'tan sonra koordinasyon kazanımları platoya ulaşır
- MAST çalışması: 1,642 trace, %41-86.7 başarısızlık, %36.9'u koordinasyon çöküşü

## Bileşik Güvenilirlik Sorunu
| Per-step | 10 adım | 20 adım |
|----------|---------|---------|
| %99 | %90.4 | %81.8 |
| %95 | %59.9 | %35.8 |
| Token: 1 agent 10K | 4 agent 35K (3.5x) |

## 3 Çalışan Pattern

### 1. Plan-and-Execute (Klarna modeli)
- Güçlü model planlar, ucuz modeller uygular → %90 maliyet düşüşü
- ✅ Net hedef, sıralı adımlar: dokuman işleme, müşteri hizmetleri
- ❌ Ortam değişiyorsa plan geçersiz kalır

### 2. Supervisor-Worker
- Merkezi supervisor: routing, delegasyon, izleme, birleştirme
- Hata amplifikasyonunu bastırır (DeepMind doğrulaması)
- ✅ Heterojen görevler, farklı uzmanlıklar
- ❌ Supervisor darboğaz olursa monolite döner → bounded autonomy

### 3. Swarm (Merkezi olmayan handoff)
- Supervisor yok, agent'lar bağlama göre birbirine devreder
- OpenAI Agents SDK: tanımlı handoff yolları + guardrail
- ✅ Yüksek hacim, iyi tanımlı iş akışları
- ❌ Karmaşık handoff graph'ları → distributed tracing şart

## Framework Karşılaştırma
- **LangGraph:** Graph-based state machine, 34.5M/ay download, Klarna kullanıyor
- **OpenAI Agents SDK:** Swarm pattern, handoff odaklı
- **CrewAI:** Rol tabanlı, hızlı prototip

## Emin Değilsen
- Tek well-prompted agent ile başla
- Plan-and-Execute + LangGraph ilk seçim
- Agent ekle sadece kanıtlanmış ihtiyaç varsa

---

## 🎯 Anahtar Çıkarım
> Multi-agent başarısının %90'ı topoloji seçimine bağlı, agent sayısına değil. "Daha fazla agent = daha iyi" yanılsaması projeleri öldürüyor. Klarna vs iptal edilen projelerin farkı: yapısal tasarım, maliyet kontrolü ve "yeterince basit" olma cesareti.
