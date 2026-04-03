---
layout: summary
title: "The Multi-Agent Trap"
date: 2026-03-18
source: "https://towardsdatascience.com/the-multi-agent-trap/"
category: "Multi-Agent Systems"
type: "Makale"
---

## TL;DR
"Daha fazla agent = daha iyi" değil. Yapısız multi-agent sistemler hataları **17.2 kata kadar** artırıyor. Çalışan 3 pattern var: **Plan-and-Execute** (Klarna modeli, %90 maliyet düşüşü), **Supervisor-Worker** (merkezi koordinasyon), **Swarm** (supervisor'sız handoff). 5 ölümcül hata modu projeleri öldürüyor: bileşik güvenilirlik çöküşü, koordinasyon vergisi (%36.9), maliyet patlaması, güvenlik açıkları (%73 prompt injection), sonsuz retry. En çarpıcı veri: firmaların %89'u AI'dan sıfır verimlilik artışı gördü — çünkü AI'ı araç olarak kullandılar. Klarna gibi AI'ı **işgücü** olarak yapılandıranlar 60M$ tasarruf etti. Fark teknoloji değil, **mimari**.

---

## Problem
"Karmaşık işi agent'lara böl" sezgisi cazip ama tehlikeli. Google DeepMind araştırması: **yapılandırılmamış multi-agent ağlar, hataları tek agent'a kıyasla 17.2 kata kadar artırıyor.** Gartner tahmini: 2027 sonuna kadar agentic AI projelerinin %40'ından fazlası iptal edilecek.

## Bileşik Güvenilirlik Problemi
Adım başına %95 başarı bile zincirleme çöküşe yol açar:
- 10 adım → %59.9 toplam başarı
- 20 adım → %35.8 toplam başarı

Token maliyeti de katlanır: tek agent'ta 10K token → 4 agent'ta 35K token (3.5x çarpan).

## Çalışan 3 Multi-Agent Paterni

**1. Plan-and-Execute (Klarna modeli)**
- Güçlü model plan yapar, ucuz modeller uygular
- Maliyeti %90'a kadar düşürür
- ✅ Sıralı adımlara ayrılan görevler (müşteri hizmetleri, doküman işleme)
- ❌ Ortası değişen, volatile ortamlar

**2. Supervisor-Worker**
- Bir supervisor yönlendirir, worker'lar uzmanlık alanlarında çalışır
- 17x hata amplifikasyonunu bastırır
- ✅ Farklı uzmanlık gerektiren heterojen görevler
- ❌ Supervisor darboğaz olursa monolite döner

**3. Swarm (Merkezi olmayan el değiştirme)**
- Supervisor yok, agent'lar bağlama göre birbirine devreder
- OpenAI Agents SDK bu pattern'i guardrail'lerle implemente eder
- ✅ Yüksek hacimli, iyi tanımlı iş akışları
- ❌ Karmaşık handoff grafları — distributed tracing şart

## 5 Ölümcül Hata Modu

1. **Bileşik Güvenilirlik Çöküşü** → Zinciri 5 adımın altında tut, 3. ve 5. adımda doğrulama agent'ı koy
2. **Koordinasyon Vergisi** (tüm hataların %36.9'u) → Agent'lar arası açık input/output kontratları, implicit paylaşımlı state yok
3. **Maliyet Patlaması** → Agent ve workflow başına hard token bütçesi, circuit breaker'lar
4. **Güvenlik Açıkları** (üretim sistemlerinin %73'ünde prompt injection) → Her agent sınırında input sanitization, red-team testi
5. **Sonsuz Retry Döngüsü** → Max 3 retry, exponential backoff, dead-letter queue, cycle check

## Framework Karşılaştırması

| Framework | Felsefe | Güçlü Yan | Zayıf Yan |
|-----------|---------|-----------|-----------|
| **LangGraph** | Graf tabanlı state machine | En battle-tested, Klarna kullanıyor | Öğrenme eğrisi dik |
| **CrewAI** | Rol tabanlı takımlar | En düşük giriş bariyeri, %40 daha hızlı deploy | Cycle ve karmaşık state desteği sınırlı |
| **OpenAI Agents SDK** | Hafif primitifler | Python + TS/JS eşit destek | OpenAI model'lerine sıkı bağımlılık |

> Emin değilsen: **Plan-and-Execute + LangGraph** ile başla.

## Tool vs Worker: 60 Milyon Dolarlık Fark
NBER araştırması: Firmaların %89'u AI'dan sıfır verimlilik artışı gördü — çünkü AI'ı **araç** olarak kullandılar (haftada 1.5 saat copilot). Klarna gibi kazananlar AI'ı **işgücü** olarak konumlandırdı: yapılandırılmış iş akışlarında otonom agent'lar, karar sınırlarında insan denetimi.

---

## 🎯 Anahtar Çıkarım
> Fark teknoloji değil, mimari. Yapılandırılmamış multi-agent sistemler hataları 17x artırırken, doğru pattern (Plan-and-Execute, Supervisor-Worker, Swarm) + bileşik güvenilirlik matematiği + 5 hata moduna karşı önlem alan sistemler milyonlarca dolar tasarruf sağlıyor. AI'ı araç değil işgücü olarak konumlandıran şirketler kazanıyor.
