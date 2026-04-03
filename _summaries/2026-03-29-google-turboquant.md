---
layout: summary
title: "Google TurboQuant: 6x Az Bellek, 8x Hız"
date: 2026-03-29
source: "https://www.donanimhaber.com/google-dan-yapay-zekada-devrim-turboquant-ile-yuksek-sikistirma--203657"
category: "Google & Gemini"
type: "Makale"
---

## TL;DR
Google'ın TurboQuant algoritması, LLM'lerin key-value cache'ini doğruluk kaybı olmadan sıkıştırarak 6x az bellek kullanımı ve 8x hız artışı sağlıyor. İki aşamalı çalışıyor: PolarQuant (kartezyen → kutupsal koordinat dönüşümü) ve QJL (hata düzeltme). Ek eğitim gerektirmeden mevcut modellere uygulanabilir.

---

## Key Points
- Key-value cache'i hedefliyor — modelin "kopya kağıdı", tekrar hesaplama önler
- PolarQuant: vektörleri kartezyen (XYZ) yerine kutupsal koordinatlara dönüştürür — yarıçap + açı
- QJL (Quantized Johnson-Lindenstrauss): her vektörü tek bit (+1/-1) ile temsil, hata düzeltme katmanı
- 3-bit seviyesine kadar sıkıştırma — ek eğitim gerektirmiyor
- 4-bit TurboQuant: H100'da 32-bit'e kıyasla 8x hız
- Gemma ve Mistral modelleri üzerinde test edildi — kalite korunuyor
- Mobil cihazlar için büyük önem — yerel AI inference mümkün hale geliyor

---

## 🎯 Anahtar Çıkarım
> TurboQuant, AI modellerini kalite kaybı olmadan dramatik şekilde küçültüp hızlandırarak, özellikle mobil cihazlarda ve edge computing'de yerel AI çalıştırmanın önünü açıyor.
