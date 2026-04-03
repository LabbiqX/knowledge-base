---
layout: summary
title: "Confucius Code Agent: Scaffolding Beats Model Size"
date: 2026-03-29
source: "https://www.marktechpost.com/2026/01/09/meta-and-harvard-researchers-introduce-the-confucius-code-agent-cca-a-software-engineering-agent-that-can-operate-at-large-scale-codebases/"
category: "LLM & Models"
type: "Makale"
---

## TL;DR
Meta and Harvard released the Confucius Code Agent, proving that strong scaffolding can outweigh model size: Claude 4.5 Sonnet with Confucius reaches 52.7 on SWE-Bench Pro, surpassing Claude 4.5 Opus with weaker scaffold (52.0). Key innovations: hierarchical working memory for long-horizon coding, persistent note-taking as cross-session memory (reduces tokens 104k→93k), and a meta-agent that automatically designs and tunes agent configurations.

---

## Key Points
- **Scaffolding > model size:** Claude 4.5 Sonnet + Confucius (52.7) beats Claude 4.5 Opus + standard scaffold (52.0) on SWE-Bench Pro
- **Hierarchical working memory:** partitions trajectory into scopes, summarizes past steps, compresses context
- **Persistent notes:** structured Markdown from execution traces; reusing notes reduces turns 64→61, tokens 104k→93k, improves resolve 53.0→54.4
- **Tool sophistication matters:** advanced context features raise Resolve@1 from 44.0 to 51.6 with same model
- **Meta-agent:** LLM-guided build-test-improve loop for automatic agent design
- SWE-Bench Verified: 74.6 with Claude 4 Sonnet (vs 66.6 SWE-Agent, 72.8 OpenHands)
- Stable performance across file counts: 57.8 (1-2 files) to 44.4 (10+ files)
- Full scaffold open-sourced via Confucius SDK

---

## 🎯 Anahtar Çıkarım
> Confucius Code Agent, "model zekası yerine scaffold zekası" tezini kanıtlıyor — iyi tasarlanmış memory, tool management ve meta-agent, daha küçük modeli daha büyüğünün önüne geçiriyor.
