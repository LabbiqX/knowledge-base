---
layout: summary
title: "Building Multi-Agent Applications with Deep Agents"
date: 2026-03-29
source: "https://blog.langchain.com/building-multi-agent-applications-with-deep-agents/"
category: "Multi-Agent Systems"
type: "Makale"
---

## TL;DR
LangChain's Deep Agents framework introduces two primitives for multi-agent systems: **subagents** (isolated workers with their own context windows) and **skills** (progressive disclosure via SKILL.md files). Subagents solve context bloat by delegating complex tasks to separate context windows, while skills avoid token waste by loading detailed instructions only when needed.

---

## Key Points
- **Context bloat** is the core problem: models struggle as context windows fill up ("dumb zone")
- **Subagents** run with isolated context — main agent only gets final result, not intermediate tool calls
- Subagent use cases: context preservation, specialization, multi-model (different models), parallelization
- Built-in **general-purpose subagent** mirrors main agent capabilities for simple context isolation
- **Skills** use the agentskills.io spec — descriptions pre-loaded, full body loaded on demand
- Best practices: clear descriptions, detailed system prompts, minimal focused tool sets
- Both patterns composable: subagents can use skills internally
- Code examples provided for `create_deep_agent()` with subagents and skills configuration

---

## 🎯 Anahtar Çıkarım
> Multi-agent sistemleri karmaşık olmak zorunda değil — subagents ile context yönetimi, skills ile progressive disclosure sağlayarak basit building block'lardan güçlü sistemler kurulabilir.
