---
layout: summary
title: "HunyuanOCR: Tencent's 1B Parameter End-to-End OCR Expert VLM"
date: 2026-03-29
source: "https://www.marktechpost.com/2025/11/26/tencent-hunyuan-releases-hunyuanocr-a-1b-parameter-end-to-end-ocr-expert-vlm/"
category: "AI Agent Architecture"
type: "Makale"
---

## TL;DR
Tencent released HunyuanOCR, a 1B parameter vision-language model specialized for OCR that matches or surpasses much larger models (Gemini 2.5, Qwen3 VL) on OCR tasks. It handles spotting, parsing, information extraction, VQA, and translation in a single end-to-end pipeline without external layout analysis. Trained on 200M+ image-text pairs across 130+ languages and 9 real-world scenarios, it achieves 94.1 on OmniDocBench and 860 on OCRBench — SOTA for sub-3B models.

---

## Key Points
- 1B parameters: 0.4B Native Resolution ViT + Adaptive MLP Connector + 0.5B Language Model
- Single end-to-end pipeline: no external layout analysis or post-processing
- 200M+ image-text pairs, 130+ languages, 9 scenarios (docs, street views, handwriting, video frames)
- XD RoPE: 4-subspace positional embeddings for 1D text + 2D layout + 3D spatiotemporal
- 4-stage training + GRPO reinforcement learning with verifiable rewards
- OmniDocBench: 94.1 overall; OCRBench: 860 (SOTA for sub-3B)
- Won ICDAR 2025 DIMT competition Track 2.2
- Open source: model weights on HuggingFace, code on GitHub

---

## 🎯 Anahtar Çıkarım
> HunyuanOCR, 1B parametre ile dev modelleri OCR'da geçerek "küçük ve uzmanlaşmış model > büyük genel model" tezini doğruluyor — production OCR için ciddi bir alternatif.
