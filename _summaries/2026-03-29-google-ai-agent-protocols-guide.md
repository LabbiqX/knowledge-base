---
layout: summary
title: "Developer's Guide to AI Agent Protocols"
date: 2026-03-29
source: "https://developers.googleblog.com/developers-guide-to-ai-agent-protocols/"
category: "AI Agent Architecture"
type: "Makale"
---

## TL;DR
Google, AI agent protokolleri dünyasındaki kısaltma karmaşasını (MCP, A2A, UCP, AP2, A2UI, AG-UI) açıklayan kapsamlı bir rehber yayınladı. Bir restoran tedarik zinciri senaryosu üzerinden, sıfırdan başlayarak her protokolü tek tek ekleyerek: envanter kontrolü (MCP), uzman agent'lardan fiyat teklifi alma (A2A), sipariş verme (UCP) ve güvenli ödeme işlemlerini gösteriyorlar.

---

## Key Points
- **MCP (Model Context Protocol):** Agent'ları veri kaynaklarına bağlıyor; yüzlerce sunucu için tek standart bağlantı kalıbı. ADK'da McpToolset ile kullanılıyor
- **A2A (Agent2Agent Protocol):** Agent'ların birbirini keşfetmesi ve iletişimi. Her agent `.well-known/agent-card.json` yayınlıyor
- **UCP (Universal Commerce Protocol):** Alışveriş yaşam döngüsünü standartlaştırıyor; REST, MCP, A2A, EP üzerinden çalışıyor
- ADK (Agent Development Kit) ile hepsi birkaç satır kodla entegre
- Senaryo: Sıfırdan hallüsinasyon yapan LLM → gerçek envanter, fiyat teklifi, sipariş, ödeme
- `to_a2a()` ile herhangi bir ADK agent'ı A2A servisine dönüştürülebilir

---

## 🎯 Anahtar Çıkarım
> AI agent protokolleri birbirini tamamlıyor, rakip değil — MCP veri erişimi, A2A agent iletişimi, UCP ticaret standardizasyonu sağlıyor ve ADK hepsini birleştiren çatı oluyor.
