---
layout: summary
title: "Cursor'ın \"AI ile Tarayıcı Yaptık\" İddiası: Repo'yu Kontrol Et"
date: 2026-03-29
source: "https://www.theregister.com/2026/01/26/cursor_opinion/"
category: "AI Coding Tools"
type: "Makale"
---

## TL;DR
Cursor CEO'su "GPT-5.2 ile 3M+ satır kod, sıfırdan Rust tabanlı tarayıcı yaptık" dedi. Gerçek: kod zar zor derleniyor, çoğu zaman çalışmıyor, CI geçmiyor, sayfa açmak ~1 dakika sürüyor. "From scratch" iddiasına rağmen Servo ve QuickJS'e bağımlılık var. 10-20 trilyon token, milyonlarca dolarlık maliyet — sonuç: yarı-işlevsel bir demo.

---

## Key Points
- Cursor CEO: "We built a browser with GPT-5.2" — 3M+ satır, Rust, from scratch
- Gerçek: geliştiriciler klonladı → derlenmedi, CI başarısız, performans korkunç (~1 dakika sayfa açma)
- Servo (Rust rendering engine) ve QuickJS bağımlılığı — "from scratch" değil
- Tahmini maliyet: 10-20T token, milyon dolarlarca
- Servo maintainer: "uniquely bad design that could never support a real-world web engine"
- Hype, metodolojiye gömülü: iç deneme → pazarlama milestone'u olarak sunuldu
- "AI uncanny valley for developers": autocomplete olarak harika ama spec-to-shipping değil
- "Demo ≠ deliverable" — CI, reproducible build, gerçek benchmark yoksa inanma

---

## 🎯 Anahtar Çıkarım
> AI coding başarı hikayeleri karşısında "repo'yu klonla ve dene" altın kural — pazarlama sizzle reel'i ile gerçek deliverable arasındaki uçurum hâlâ devasa.
