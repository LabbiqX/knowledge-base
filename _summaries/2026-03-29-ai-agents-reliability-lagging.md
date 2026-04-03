---
layout: summary
title: "AI Agents Are Getting More Capable, But Reliability Is Lagging"
date: 2026-03-29
source: "https://fortune.com/2026/03/24/ai-agents-are-getting-more-capable-but-reliability-is-lagging-narayanan-kapoor/"
category: "AI Agent Architecture"
type: "Haber"
---

## TL;DR
Princeton araştırmacıları Kapoor ve Narayanan, AI agent güvenilirliğini sistematik olarak benchmark'layan bir araştırma yayınladı. Dört boyut: tutarlılık, dayanıklılık, kalibrasyon, güvenlik. Güvenilirlik doğruluktan çok daha yavaş gelişiyor — genel agentic benchmark'ta yarı hızda, müşteri hizmeti benchmark'ında yedide bir! En iyi modeller %85 güvenilirlik, ama alt metriklerde ciddi sorunlar var.

---

## Key Points
- Güvenilirlik 4 boyut: consistency (tutarlılık), robustness (dayanıklılık), calibration (kalibrasyon), safety (güvenlik)
- 14 alt metrik, GPT-5.2, Claude Opus 4.5, Gemini 3 Pro test edildi
- Claude Opus 4.5 ve Gemini 3 Pro en iyi: %85 genel güvenilirlik
- Gemini 3 Pro: doğruluk tahmini %52, felaket hata önleme %25
- Claude Opus 4.5: en tutarlı ama sadece %73
- Güvenilirlik iyileşme hızı / doğruluk iyileşme hızı: 1/2 (genel) ile 1/7 (müşteri hizmeti)
- Zincirlenen AI araçlarda güvenilirlik dramatik düşüyor: mamografi(%90) + transkripsiyon(%85) + tanı(%97) = %74 birleşik
- Otonom sistemler için %90 başarı + %10 öngörülemeyen hata kabul edilemez

---

## 🎯 Anahtar Çıkarım
> AI agent'lar ortalama doğrulukta hızla gelişiyor ama güvenilirlik çok geride kalıyor — tam otonom kullanım için doğruluk yetmez, tutarlılık, dayanıklılık ve güvenlik metrikleri de benchmark'lanmalı ve optimize edilmeli.
