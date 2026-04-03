---
layout: summary
title: "Hierarchical Planner AI Agent: Açık Kaynak LLM ile Yapılandırılmış Multi-Agent"
date: 2026-03-29
source: "https://www.marktechpost.com/2026/02/27/a-coding-implementation-to-build-a-hierarchical-planner-ai-agent-using-open-source-llms-with-tool-execution-and-structured-multi-agent-reasoning/"
category: "Multi-Agent Systems"
type: "Makale"
---

## TL;DR
Qwen2.5-1.5B-Instruct gibi küçük açık kaynak model kullanarak Planner→Executor→Aggregator mimarisinde hiyerarşik agent sistemi inşa eden hands-on tutorial. Planner hedefi adımlara ayırır, Executor her adımı reasoning veya Python tool execution ile çözer, Aggregator sonuçları sentezler.

---

## Key Points
- 3 agent mimarisi: Planner (görev ayrıştırma), Executor (uygulama), Aggregator (sentez)
- Qwen2.5-1.5B-Instruct — 4-bit quantization ile GPU'da çalıştırılabilir
- Planner: JSON çıktı zorunluluğu — her adım için id, title, instruction, tool, expected_output
- Executor: tool="python" ise kod üretip çalıştırır, tool="llm" ise reasoning yapar
- Python sandbox: exec() ile güvenli kod yürütme, stdout/error yakalama
- Robust JSON parsing: fenced blocks + inline JSON desteği
- Context window yönetimi: prior results kompakt şekilde executor'a aktarılır

---

## 🎯 Anahtar Çıkarım
> Küçük açık kaynak modeller bile Planner→Executor→Aggregator hiyerarşisiyle karmaşık görevleri yapılandırılmış şekilde çözebilir — anahtar, doğru mimari ve deterministik tool entegrasyonu.
