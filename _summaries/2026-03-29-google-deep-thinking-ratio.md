---
layout: summary
title: "Google Deep-Thinking Ratio: LLM Doğruluğunu Artırırken Maliyeti Yarıya İndirmek"
date: 2026-03-29
source: "https://www.marktechpost.com/2026/02/21/a-new-google-ai-research-proposes-deep-thinking-ratio-to-improve-llm-accuracy-while-cutting-total-inference-costs-by-half/"
category: "Google & Gemini"
type: "Makale"
---

## TL;DR
Google araştırması, "daha uzun düşünme = daha iyi sonuç" varsayımını çürütüyor. Token sayısı doğrulukla negatif korelasyon gösteriyor (r=-0.59). Bunun yerine Deep-Thinking Ratio (DTR) — modelin derin katmanlarında tahminini ciddi şekilde revize ettiği token oranı — doğrulukla güçlü pozitif korelasyon gösteriyor (r=0.683). Think@n yöntemiyle %50 maliyet düşüşüyle daha yüksek doğruluk elde ediliyor.

---

## Key Points
- Token sayısı ≠ düşünme kalitesi — uzun CoT "overthinking" yapabilir (r=-0.59 doğrulukla)
- **Deep-Thinking Tokens:** Modelin derin katmanlarında (son %15) tahminini ciddi şekilde revize ettiği tokenlar
- **DTR:** Deep-thinking token oranı — doğrulukla r=0.683 korelasyon
- Jensen-Shannon Divergence ile ara katman tahminleri vs final karşılaştırması
- **Think@n:** Sadece 50 prefix token'dan DTR hesaplayıp düşük DTR'li adayları erken durdurma
- AIME 2025 sonucu: Think@n %94.7 doğruluk (vs Cons@n %92.7), maliyet %49 düşüş
- DeepSeek-R1-70B, Qwen3-30B-Thinking, GPT-OSS-120B üzerinde test edildi

---

## 🎯 Anahtar Çıkarım
> "Daha fazla token = daha akıllı" değil — gerçek düşünme derinliği modelin iç katmanlarında ölçülebilir ve bu metrik sayesinde %50 maliyet tasarrufu ile daha yüksek doğruluk mümkün.
