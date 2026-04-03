---
layout: summary
title: "How Agent Handoffs Work in Multi-Agent Systems"
date: 2026-03-29
source: "https://towardsdatascience.com/how-agent-handoffs-work-in-multi-agent-systems/"
category: "Multi-Agent Systems"
type: "Makale"
---

## TL;DR
Multi-agent sistemlerde handoff = bir agent'ın kontrolü, sorumluluğu ve bağlamı dinamik olarak başka bir agent'a devretmesi. LangGraph'te iki mekanizma: Conditional Edges (statik routing — sadece yönlendirme) ve Command Object (dinamik — state güncelleme + yönlendirme bir arada). Supervisor pattern ile routing yapılır, her worker agent özel araç ve prompt ile uzmanlaşır.

---

## Handoff Nedir?
- Bir agent'ın işini bitirip kontrolü diğer agent'a aktardığı an
- Amaç: görevi en uygun agent'a yönlendirme
- State (kısa süreli hafıza) transfer edilir — önceki bağlam korunur

## Supervisor Pattern
- Merkezi supervisor agent → kullanıcı niyetini analiz → uygun worker'a yönlendir
- Worker agent'lar özel araçlar + prompt ile uzmanlaşmış
- Routing kriterleri supervisor prompt'unda açıkça tanımlanır

## LangGraph'te İki Handoff Mekanizması

### 1. Conditional Edges (Statik Routing)
- Node çıktısı → conditional edge fonksiyonu → sonraki node kararı
- `add_conditional_edges(source, path=routing_function)`
- Routing mantığı edge'lerde yaşar
- **Ne zaman:** Sadece yönlendirme lazım, state değişikliği yok

### 2. Command Object (Dinamik Handoff)
- Node doğrudan `Command(goto="next_agent", update={...})` döner
- State güncelleme + routing tek işlemde
- **Edgeless graph:** Routing mantığı node'larda, edge tanımlamaya gerek yok
- **Ne zaman:** Routing + state güncellemesi aynı anda gerekli (çoğu gerçek senaryo)

## Pratik Örnek: Gayrimenkul Asistanı
- Supervisor: Gayrimenkul yöneticisi
- Worker 1: Mülk profil agent (detay sorguları)
- Worker 2: İşlem geçmişi agent (işlem + piyasa trendleri)
- Akış: Kullanıcı sorusu → supervisor analiz → uygun worker'a handoff → yanıt

## Önemli Notlar
- Tek agent çok fazla araç/bağlam ile kötü karar verir → multi-agent çözüm
- LLM'den structured output (SupervisorDecision) ile handoff kararı
- Command ile handoff sırasında property_name gibi bağlam bilgisi de aktarılabilir

---

## 🎯 Anahtar Çıkarım
> Agent handoff'ların kalitesi multi-agent sistemin kalitesini belirler. Command Object yaklaşımı conditional edge'lere göre daha temiz ve esnek — state güncelleme ile routing'i birleştirerek handoff mantığını node içinde tutuyor. Gerçek dünya senaryolarında Command tercih edilmeli.
