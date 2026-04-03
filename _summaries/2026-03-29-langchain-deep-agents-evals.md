---
layout: summary
title: "How We Build Evals for Deep Agents"
date: 2026-03-29
source: "https://blog.langchain.com/how-we-build-evals-for-deep-agents/"
category: "Agent Evaluation"
type: "Makale"
---

## TL;DR
LangChain, Deep Agents için eval sistemi kurma deneyimlerini paylaşıyor. Ana prensip: "Daha fazla eval ≠ daha iyi agent" — hedefli, davranış odaklı eval'ler oluşturmak gerekiyor. Veri kaynakları: dogfooding, harici benchmark'lar (Terminal Bench 2.0, BFCL) ve el yapımı testler. Metrikler: correctness, step ratio, tool call ratio, latency ratio ve solve rate.

---

## Key Points
- Her eval, agent davranışını şekillendiren bir "vektör" — düşüncesizce yüzlerce test eklemek yanıltıcı
- Eval kategorileri: file_operations, retrieval, tool_use, memory, conversation, summarization, unit_tests
- Veri kaynakları: dogfooding trace'leri, harici benchmark adaptasyonları, el yazımı testler
- Doğruluk ölçümü: custom assertion, exact matching, LLM-as-a-judge (semantic doğruluk için)
- Verimlilik metrikleri: step ratio (gözlenen/ideal adım), tool call ratio, latency ratio
- Solve rate = beklenen adım sayısı / gözlenen süre (yanlış çözümlerde 0)
- Tüm eval çalıştırmaları LangSmith'e trace edilir — ekip genelinde paylaşılan sorumluluk

---

## 🎯 Anahtar Çıkarım
> Etkili agent eval'leri, üretimde önem verdiğiniz belirli davranışları hedefli olarak ölçmeli — toplu benchmark puanları değil, doğruluk sonrası verimlilik karşılaştırması yapabilmelisiniz.
