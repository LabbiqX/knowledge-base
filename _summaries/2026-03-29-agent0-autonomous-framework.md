---
layout: summary
title: "Agent0: Fully Autonomous AI Framework That Self-Evolves Without External Data"
date: 2026-03-29
source: "https://www.marktechpost.com/2025/11/24/agent0-a-fully-autonomous-ai-framework-that-evolves-high-performing-agents-without-external-data-through-multi-step-co-evolution/"
category: "AI Agent Architecture"
type: "Makale"
---

## TL;DR
Researchers from UNC-Chapel Hill, Salesforce, and Stanford introduce Agent0, a fully data-free framework that evolves high-performing agents through co-evolution. A base LLM is cloned into a Curriculum Agent (generates tasks) and an Executor Agent (solves tasks with Python tools). They co-evolve through RL: the curriculum learns to create frontier-difficulty tasks, and the executor learns to solve them. On Qwen3 8B, it improves math benchmarks from 49.2→58.2 and general reasoning from 34.5→42.1 without any external data.

---

## Key Points
- Two agents from one base model: Curriculum Agent (task generator) + Executor Agent (solver with code interpreter)
- Co-evolution loop: curriculum generates harder tasks as executor improves
- ADPO (Ambiguity Dynamic Policy Optimization): stable RL with pseudo-labels from majority voting
- No external datasets or human annotations needed
- Qwen3 8B: +18% math, +24% general reasoning improvement
- Outperforms R Zero (+6.4pp), Absolute Zero (+10.6pp), Socratic Zero
- Multi-turn tool-integrated rollouts with sandboxed Python execution
- Stable improvement across 3 co-evolution iterations (no collapse)

---

## 🎯 Anahtar Çıkarım
> Agent0, "AI'ın kendi müfredatını oluşturup kendini eğitmesi" paradigmasının çalıştığını kanıtlıyor — dış veri olmadan %18-24 reasoning artışı, self-evolving agent'ların geleceğine güçlü bir sinyal.
