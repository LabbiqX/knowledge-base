---
layout: summary
title: "Agentic AI with Control-Plane Architecture"
date: 2026-03-29
source: "https://www.marktechpost.com/2025/11/28/a-coding-guide-to-design-an-agentic-ai-system-using-a-control-plane-architecture-for-safe-modular-and-scalable-tool-driven-reasoning-workflows/"
category: "AI Agent Architecture"
type: "Makale"
---

## TL;DR
A coding tutorial for building an agentic AI system using the control-plane design pattern. The control plane acts as central orchestrator that coordinates tools, manages safety rules (max tools per request, allowed tool whitelist), and structures the reasoning loop. Implements RAG retrieval, modular tool registry (knowledge search, assessment, learner profile, logging), safety validation, and Claude-powered synthesis agent.

---

## Key Points
- Control plane pattern: central orchestrator for tool coordination and safety
- Safety rules: max tools per request, allowed tools whitelist, execution limits
- Tool registry: modular capabilities (search_knowledge, assess_understanding, update_learner_profile, log_interaction)
- SimpleRAGRetriever with TF-IDF embeddings and cosine similarity
- Every request validated before routing to tool functions
- Execution log for full transparency and audit trail
- TutorAgent uses Anthropic API for synthesis
- Planning phase: analyzes query keywords → selects appropriate tools → executes → synthesizes

---

## 🎯 Anahtar Çıkarım
> Control-plane pattern, AI agent'lar için "güvenlik + modülerlik + ölçeklenebilirlik" üçlüsünü sağlıyor — her araç çağrısı doğrulanıyor, loglanıyor ve izin kontrolleri merkezi bir noktadan yönetiliyor.
