---
layout: summary
title: "Agentic Workflow ile Tool-Driven Route Optimization Tasarımı"
date: 2026-03-29
source: "https://www.marktechpost.com/2026/02/21/how-to-design-an-agentic-workflow-for-tool-driven-route-optimization-with-deterministic-computation-and-structured-outputs/"
category: "AI Agent Architecture"
type: "Makale"
---

## TL;DR
LangChain agent API'larıyla bir lojistik rota optimizasyon agent'ı inşa eden detaylı tutorial. Agent, Haversine mesafe hesaplama, hız profilleri, trafik çarpanları ve çok duraklı rota optimizasyonu için deterministik tool'lar kullanıyor. Pydantic ile structured output zorunluluğu sayesinde halüsinasyon yerine gerçek hesaplama yapılıyor.

---

## Key Points
- Deterministik tool-driven yaklaşım: agent mesafe/ETA hesaplamak yerine tool çağırır
- Haversine formülü ile gerçek mesafe, hız profilleri (highway/arterial/local), trafik çarpanı
- Çok duraklı rota: waypoint permütasyonları ile optimal rota bulma
- Pydantic structured output: RoutePlan, RouteDecision modelleri — downstream uyumlu
- @tool dekoratörleri: list_sites, get_site_details, suggest_site, compute_direct_route, optimize_route
- gpt-4o-mini ile low-cost implementasyon

---

## 🎯 Anahtar Çıkarım
> "Agent'lar tahmin etmemeli, hesaplamalı" — tool-driven deterministik workflow + structured output ile halüsinasyon sorununu ortadan kaldıran pratik bir agentic tasarım örneği.
