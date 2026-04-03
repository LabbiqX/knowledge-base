---
layout: summary
title: "NVIDIA PersonaPlex-7B: Gerçek Zamanlı Full-Duplex Konuşma Modeli"
date: 2026-03-29
source: "https://www.marktechpost.com/2026/01/17/nvidia-releases-personaplex-7b-v1-a-real-time-speech-to-speech-model-designed-for-natural-and-full-duplex-conversations/"
category: "LLM & Models"
type: "Makale"
---

## TL;DR
NVIDIA'nın PersonaPlex-7B, geleneksel ASR→LLM→TTS pipeline'ını tek bir Transformer modeliyle değiştiren full-duplex konuşma modeli. Aynı anda dinleyip konuşabiliyor, doğal kesintileri yönetiyor ve persona kontrolü sunuyor. Moshi mimarisi üzerine inşa edilmiş, MIT lisanslı.

---

## Key Points
- Tek model: ASR→LLM→TTS pipeline'ını birleştirir — latency azalır
- Full-duplex: aynı anda dinleme + konuşma, barge-in, overlap, hızlı turn-taking
- Dual-stream Transformer: kullanıcı audio + agent speech/text aynı model state'i paylaşır
- Persona kontrolü: voice prompt (ses, stil, prosodi) + text prompt (rol, bağlam, iş bilgisi)
- Helium backbone + Mimi speech encoder/decoder, 24kHz
- Eğitim: 7,303 Fisher corpus konuşması + 145K sentetik dialog
- FullDuplexBench sonuçları: smooth turn-taking TOR 0.908, interruption TOR 0.950
- MIT lisans + NVIDIA Open Model License

---

## 🎯 Anahtar Çıkarım
> PersonaPlex, sesli AI asistanları "sırayla konuşma"dan gerçek insan benzeri "aynı anda konuşma" seviyesine taşıyarak, customer service ve kişisel asistanlar için devrim niteliğinde.
