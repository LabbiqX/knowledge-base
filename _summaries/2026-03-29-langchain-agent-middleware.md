---
layout: summary
title: "How Middleware Lets You Customize Your Agent Harness"
date: 2026-03-29
source: "https://blog.langchain.com/how-middleware-lets-you-customize-your-agent-harness/"
category: "AI Agent Architecture"
type: "Makale"
---

## TL;DR
LangChain, agent harness'larını özelleştirmek için "Agent Middleware" konseptini tanıttı. Middleware, agent döngüsünün her aşamasında (model çağrısı öncesi/sonrası, tool çağrısı, başlangıç/bitiş) hook'lar sunarak PII redaction, dinamik tool seçimi, context summarization, retry mantığı gibi üretim gereksinimleri karşılıyor. Deep Agents tamamen bu middleware stack üzerine inşa edildi.

---

## Key Points
- **Agent Middleware Hook'ları:** before_agent, before_model, wrap_model_call, wrap_tool_call, after_model, after_agent
- **Hazır middleware'ler:** PIIMiddleware, SummarizationMiddleware, ModelRetryMiddleware, ShellToolMiddleware, LLMToolSelectorMiddleware
- **Kullanım alanları:** İş mantığı/uyumluluk, dinamik agent kontrolü, context yönetimi, production hazırlığı, toolset yönetimi
- Middleware'ler composable — birden fazla birlikte kullanılabilir
- Deep Agents: FilesystemMiddleware, SubagentMiddleware, SummarizationMiddleware, SkillsMiddleware üzerine inşa edildi
- Modeller güçlendikçe bazı middleware'ler (summarization, tool selection) modele absorbe edilecek, ama deterministic iş mantığı her zaman harness'ta kalacak

---

## 🎯 Anahtar Çıkarım
> Agent middleware, "her agent için aynı core loop ama farklı ihtiyaçlar" sorununu çözen temiz bir abstraction — modeller güçlense bile deterministic kurallar ve iş mantığı her zaman harness seviyesinde yaşayacak.
