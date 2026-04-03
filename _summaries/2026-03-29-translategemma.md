---
layout: summary
title: "TranslateGemma: A New Suite of Open Translation Models"
date: 2026-03-29
source: "https://blog.google/innovation-and-ai/technology/developers-tools/translategemma/"
category: "LLM & Models"
type: "Makale"
---

## TL;DR
Google, Gemma 3 üzerine kurulu açık kaynak çeviri modeli ailesi TranslateGemma'yı yayınladı (4B, 12B, 27B). 12B model, 27B baseline'ı geçiyor — yarı parametre ile daha iyi kalite. 55 dilde test edilmiş, ~500 ek dil çifti için eğitilmiş. Gemini'den bilgi distillation + RL ile eğitilmiş. Mobil (4B), laptop (12B) ve bulut (27B) ortamlarında çalışıyor.

---

## Temel Özellikler
- **Verimlilik:** 12B model, 27B baseline'dan daha iyi performans (MetricX/WMT24++)
- **4B model:** Mobil/edge cihazlara optimize — 12B baseline'a yakın performans
- **55 dil:** Yüksek, orta ve düşük kaynaklı diller dahil
- **~500 ek dil çifti:** Araştırmacılar için fine-tuning başlangıç noktası
- **Multimodal:** Görsel içindeki metin çevirisi de destekleniyor (Vistra benchmark)

## Eğitim Yöntemi
1. **SFT (Supervised Fine-Tuning):** İnsan çevirileri + Gemini üretimi sentetik çevirilerden oluşan çeşitli dataset
2. **RL (Reinforcement Learning):** MetricX-QE ve AutoMQM gibi ödül modelleri ile kalite iyileştirme

## Dağıtım
| Model | Hedef Ortam |
|-------|------------|
| 4B | Mobil ve edge cihazlar |
| 12B | Tüketici dizüstü bilgisayarlar |
| 27B | Tek H100 GPU veya TPU (bulut) |

## Erişim
- Kaggle, Hugging Face, Gemma Cookbook, Vertex AI

---

## 🎯 Anahtar Çıkarım
> Küçük modeller büyük modelleri geçebiliyor — doğru distillation ve RL ile. TranslateGemma 12B'nin 27B baseline'ı aşması, "daha büyük = daha iyi" varsayımını çürütüyor ve mobil/edge çeviri çözümlerinin kalitesiz olmak zorunda olmadığını gösteriyor.
