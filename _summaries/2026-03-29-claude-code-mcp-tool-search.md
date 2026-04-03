---
layout: summary
title: "Claude Code's MCP Tool Search: Lazy Loading for AI Tools"
date: 2026-03-29
source: "https://venturebeat.com/orchestration/claude-code-just-got-updated-with-one-of-the-most-requested-user-features"
category: "AI Coding Tools"
type: "Makale"
---

## TL;DR
Anthropic introduced MCP Tool Search for Claude Code, solving the "bloat" problem where AI agents wasted 33%+ of their context window loading tool definitions they never used. The feature implements lazy loading — dynamically fetching tool definitions only when needed — reducing token usage from ~134k to ~5k (85% reduction) while improving model accuracy from 49% to 74% on MCP evaluations for Opus 4.

---

## Key Points
- Problem: MCP servers with 50+ tools consumed 67k+ tokens before user even typed a prompt
- Single Docker MCP server: 135 tools consuming 125,000 tokens just for definitions
- Solution: Auto-detect when tool descriptions exceed 10% of context, switch to lightweight search index
- Token savings: from ~134k to ~5k (85% reduction) in internal testing
- Accuracy improvement: Opus 4 from 49% → 74%, Opus 4.5 from 79.5% → 88.1% on MCP evals
- `server instructions` field now critical — acts as metadata for tool discovery
- Removes soft cap on agent capability; thousands of tools with no penalty until actually used
- Shifts "context economy" from scarcity model to access model
- Boris Cherny: "Every Claude Code user just got way more context, better instruction following"

---

## 🎯 Anahtar Çıkarım
> MCP Tool Search, AI agent'lar için "lazy loading" getiriyor — binlerce araca erişim sağlarken context window israfını %85 azaltıyor ve model doğruluğunu dramatik şekilde artırıyor.
