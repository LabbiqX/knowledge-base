---
layout: summary
title: "Recursive Language Models (RLMs): 10M+ Token Context via Code"
date: 2026-03-29
source: "https://www.marktechpost.com/2026/01/02/recursive-language-models-rlms-from-mits-blueprint-to-prime-intellects-rlmenv-for-long-horizon-llm-agents/"
category: "RAG & Knowledge"
type: "Makale"
---

## TL;DR
Recursive Language Models treat the entire prompt as an external Python variable instead of feeding it into the context window. The root model writes code to inspect, partition, and recursively process the context through sub-LLM calls, extending effective context to 10M+ tokens (100x beyond base window). On OOLONG Pairs, GPT-5's direct F1 is 0.04 while RLM achieves 58.00. Prime Intellect operationalized this as RLMEnv with parallel sub-query batching.

---

## Key Points
- Prompt loaded as string variable in Python REPL — model never reads full context directly
- Root model writes code to slice, search, partition, and recursively call sub-LLMs
- Extends effective context to 10M+ tokens (2 orders of magnitude beyond base window)
- GPT-5 on OOLONG Pairs: base 0.04 F1 → RLM 58.00 F1
- BrowseComp-Plus (6-11M tokens): RLM achieves ~91.33 accuracy at $0.99/query
- Behavior patterns: peek → grep-style filtering → chunk + recursive summarize → aggregate
- Prime Intellect's RLMEnv: sandboxed REPL + llm_batch for parallel sub-queries
- Both REPL and recursion critical; ablation shows REPL-only helps but full recursion needed for hard tasks
- Future: combine with RL for learned chunking/recursion policies

---

## 🎯 Anahtar Çıkarım
> RLM'ler, long-context problemini "daha büyük context window" yerine "programatik context yönetimi" ile çözüyor — 10M+ token'lık ortamları 272K token'lık modelle işleyebilmek, paradigma değişikliği.
