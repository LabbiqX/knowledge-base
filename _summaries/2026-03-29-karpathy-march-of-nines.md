---
layout: summary
title: "Karpathy's March of Nines: Why 90% AI Reliability Isn't Even Close to Enough"
date: 2026-03-29
source: "https://venturebeat.com/technology/karpathys-march-of-nines-shows-why-90-ai-reliability-isnt-even-close-to"
category: "AI Agent Architecture"
type: "Makale"
---

## TL;DR
Karpathy's "March of Nines" framework shows that in a 10-step agentic workflow, 90% per-step reliability yields only 35% end-to-end success (~6.5 failures/day). You need 99.99% per-step to reach enterprise-grade reliability (~1 failure every 3.3 months). Each additional nine requires comparable engineering effort: bounded workflows, strict interfaces, resilient dependencies, and fast operational learning.

---

## Key Points
- Math: 10-step workflow at 90% per step = 34.87% end-to-end success
- 99% per step = ~1 failure/day; 99.9% = ~1 every 10 days; 99.99% = ~1 every 3.3 months
- 9 levers for adding nines: workflow graphs, contracts at boundaries, layered validators, risk-based routing, tool calls as distributed systems, predictable retrieval, production eval pipelines, observability, autonomy sliders
- McKinsey 2025: 51% of organizations using AI had negative consequences; ~1/3 from AI inaccuracy
- Treat connectors/retrieval as first-class reliability work
- Every incident → regression test in golden set
- Default to read-only/reversible actions; fallbacks are mandatory

---

## 🎯 Anahtar Çıkarım
> The distance between a working demo (90%) and reliable enterprise software (99.99%) is enormous — each nine requires the same engineering effort. Agentic workflows compound failure exponentially; reliability is an engineering discipline, not a model feature.
