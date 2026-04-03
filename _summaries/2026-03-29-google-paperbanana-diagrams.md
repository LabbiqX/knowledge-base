---
layout: summary
title: "Google PaperBanana: Akademik Diyagram ve Grafikleri Otomatik Üreten AI Framework"
date: 2026-03-29
source: "https://www.marktechpost.com/2026/02/07/google-ai-introduces-paperbanana-an-agentic-framework-that-automates-publication-ready-methodology-diagrams-and-statistical-plots/"
category: "Google & Gemini"
type: "Makale"
---

## TL;DR
Google ve Peking Üniversitesi'nin PaperBanana framework'ü, 5 uzman AI agent ile ham metinden yayına hazır akademik diyagramlar ve istatistik grafikleri üretiyor. NeurIPS 2025 benchmark'ında baseline'lara göre %17 daha iyi genel skor, %37 daha iyi özlülük elde etti. İstatistik grafiklerde doğruluk için Matplotlib kodu üretiyor.

---

## Key Points
- 5 agent: Retriever, Planner, Stylist, Visualizer, Critic
- 2 faz: Linear Planning (referans + stil rehberi) → Iterative Refinement (3 tur Critic feedback)
- PaperBananaBench: NeurIPS 2025'ten 292 test case
- Sonuçlar: Overall +17%, Conciseness +37.2%, Readability +12.9%, Aesthetics +6.6%
- İstatistik grafiklerde image generation yerine Matplotlib kodu → %100 veri doğruluğu
- Alan bazlı estetik rehber: Agent & Reasoning → illüstratif; CV & 3D → geometrik; Generative → modüler
- "Numerical hallucination" sorununu code-based generation ile çözüyor

---

## 🎯 Anahtar Çıkarım
> PaperBanana, araştırmacıların en sıkıcı işlerinden birini — yayın kalitesinde diyagram oluşturma — multi-agent sistemle otomatikleştirerek akademik iş akışını hızlandırıyor.
