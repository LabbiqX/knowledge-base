---
layout: summary
title: "FunctionGemma: 270M Parameter Function Calling Specialist for Edge"
date: 2026-03-29
source: "https://www.marktechpost.com/2025/12/26/from-gemma-3-270m-to-functiongemma-how-google-ai-built-a-compact-function-calling-specialist-for-edge-workloads/"
category: "AI Agent Architecture"
type: "Makale"
---

## TL;DR
Google released FunctionGemma, a 270M parameter text-only model specialized for function calling on edge devices. Based on Gemma 3 architecture, trained on 6T tokens focused on tool/API definitions and tool-use interactions. After task-specific fine-tuning, accuracy on Mobile Actions jumps from 58% to 85%. Runs offline on phones, laptops, and Jetson-class devices. Demo apps include Mobile Actions (device control), Tiny Garden (voice-controlled game), and Physics Playground (browser-based).

---

## Key Points
- 270M parameters — designed for phones, laptops, NVIDIA Jetson Nano
- Gemma 3 architecture with 256K vocabulary optimized for JSON and multilingual text
- 32K token context (shared input/output), trained on 6T tokens
- Strict chat template with control tokens for function declarations, calls, and responses
- Base accuracy: 58% → fine-tuned: 85% on Mobile Actions benchmark
- Open model under Gemma license
- Three reference demos: Mobile Actions (offline assistant), Tiny Garden (voice game), Physics Playground (browser)
- Integrated into HuggingFace, Vertex AI, LM Studio, Google AI Edge Gallery
- Key insight: small function callers need domain data more than prompt engineering

---

## 🎯 Anahtar Çıkarım
> FunctionGemma, 270M parametreyle edge cihazlarda çalışan "uzman function caller" konseptini doğruluyor — fine-tuning ile %58→%85 doğruluk, bulut bağımlılığı olmadan yerel AI agent'lar mümkün.
