---
layout: summary
title: "Karpathy's Weekend Hack: LLM Council — The Missing Layer of AI Orchestration"
date: 2026-03-29
source: "https://venturebeat.com/ai/a-weekend-vibe-code-hack-by-andrej-karpathy-quietly-sketches-the-missing"
category: "Multi-Agent Systems"
type: "Makale"
---

## TL;DR
Andrej Karpathy's weekend "vibe code" project LLM Council routes queries to 4 frontier models (GPT-5.1, Gemini 3 Pro, Claude Sonnet 4.5, Grok 4), has them peer-review each other, then a chairman model synthesizes a final answer. While built as a toy, it sketches the reference architecture for enterprise AI orchestration middleware — and reveals the gap between prototype and production-ready systems.

---

## Key Points
- Three-stage workflow: parallel generation → peer review → chairman synthesis
- Models surprisingly willing to rate competitors' responses as superior
- GPT-5.1 consistently rated best by AI models, but Karpathy preferred Gemini's condensed output
- Built on FastAPI + React + OpenRouter (model provider abstraction)
- Models treated as swappable commodities — changed via single config line
- **Missing for enterprise**: authentication, PII redaction, compliance, audit logs, circuit breakers
- Commercial AI infrastructure vendors sell the "hardening" around this core logic
- Karpathy's philosophy: "Code is ephemeral now and libraries are over"
- 99% vibe-coded — raises question if expensive software suites are still justified

---

## 🎯 Anahtar Çıkarım
> Karpathy'nin hafta sonu projesi, AI orkestrasyon katmanının temel mantığının şaşırtıcı derecede basit olduğunu gösteriyor. Gerçek karmaşıklık, güvenlik, uyumluluk ve güvenilirlik katmanlarında — tam da ticari platform şirketlerinin sattığı şey.
