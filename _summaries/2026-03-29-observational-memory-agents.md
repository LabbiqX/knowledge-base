---
layout: summary
title: "'Observational Memory' Cuts AI Agent Costs 10x and Outscores RAG"
date: 2026-03-29
source: "https://venturebeat.com/data/observational-memory-cuts-ai-agent-costs-10x-and-outscores-rag-on-long"
category: "RAG & Knowledge"
type: "Makale"
---

## TL;DR
Mastra's "observational memory" uses two background agents (Observer and Reflector) to compress conversation history into a dated observation log, eliminating retrieval entirely. It scores 94.87% on LongMemEval (vs RAG's 80.05%), cuts costs up to 10x through prompt caching, and achieves 3-40x compression ratios. Unlike RAG, it prioritizes stable, cacheable context over dynamic search.

---

## Key Points
- Observer agent compresses messages at 30K token threshold into dated observations; Reflector condenses at 40K tokens
- Text-based, no vector/graph databases required — simpler architecture
- Stable context window enables 4-10x cost reduction through prompt caching (append-only until reflection)
- Key difference from compaction: event-based decision log vs. documentation-style summaries
- Compaction loses specific decisions; observational memory preserves them
- 94.87% on LongMemEval with GPT-5-mini vs 80.05% for Mastra's own RAG
- Available in Mastra 1.0 with plugins for LangChain, Vercel AI SDK
- Best for: long-running conversations needing context across weeks/months
- Not ideal for: open-ended knowledge discovery or compliance-heavy recall

---

## 🎯 Anahtar Çıkarım
> Observational memory offers a fundamentally different approach to agent memory: instead of searching a corpus on every turn, compress and keep the context stable. The result is simpler, cheaper, and more accurate than RAG for long-running agent conversations.
