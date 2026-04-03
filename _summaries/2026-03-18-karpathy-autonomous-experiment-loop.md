---
layout: summary
title: "Karpathy's AutoResearch: 630 Satır Python ile Otonom Deney Döngüsü"
date: 2026-03-18
source: "https://thenewstack.io/karpathy-autonomous-experiment-loop/"
category: "AI Agent Architecture"
type: "Makale"
---

## TL;DR
Karpathy'nin 630 satırlık açık kaynak "AutoResearch" scripti, bir AI agent'a LLM eğitim kodu veriyor ve agent gece boyunca **otonom olarak hipotez üretip, kodu değiştirip, deney çalıştırıp, sonucu değerlendiriyor.** Bir gecede ~100 deney, 126 deneyde loss 0.9979'dan 0.9697'ye düşüyor. Shopify CEO'su Tobi Lütke bir gecede %19 skor artışı elde etti. Küçük modelde bulunan iyileştirmeler büyük modellere de transfer ediliyor. Tüm sistem: Python + LLM API + tek GPU.

---

## Konsept
AI agent'a küçük ama gerçek bir LLM eğitim ortamı ver, gece boyunca otonom deney yaptır.

## Nasıl Çalışıyor
1. **İnsan** araştırma hedefini ve kısıtları bir Markdown dosyasında tanımlar
2. **AI agent** tek bir Python eğitim scriptini (model mimarisi, optimizer, eğitim döngüsü) değiştirebilir
3. Agent kendi kodunu okur → iyileştirme hipotezi üretir → kodu değiştirir → deneyi çalıştırır → sonucu değerlendirir
4. Metrik (bits-per-byte) iyileşirse değişiklik kalır, iyileşmezse geri alınır
5. Her deney **5 dakika** duvar saati ile sınırlı → saatte ~12 deney, gecede ~100 deney

## Sonuçlar
- **126 deney** bir gecede, loss 0.9979 → 0.9697
- **~700 otonom değişiklik** iki günde, zaten iyi tuned bir projede **%11 verimlilik artışı**
- Shopify CEO Tobi Lütke: 8 saatte 37 deney, **%19 skor artışı** (0.8B model, query-expansion)
- 12 katmanlı küçük modeldeki ~650 deneyin bulguları **24 katmanlı büyük modele transfer oluyor**

## Mimari Felsefesi
- **Minimalizm:** 630 satır Python + LLM API çağrısı + tek GPU
- **Rol ayrımı:** İnsan hedef belirler (Markdown), agent kod değiştirir (Python)
- **Karşılaştırılabilirlik:** Sabit 5 dakika bütçe, model büyüklüğü değişse bile adil karşılaştırma
- **Bilimsel metod otomasyonu:** Hipotez → deney → değerlendirme → iterasyon, makine hızında

---

## 🎯 Anahtar Çıkarım
> AI agent'lar artık sadece kod yazmıyor, **bilimsel araştırma döngüsünü** de otomatikleştirebiliyor. 630 satır Python ile bir gecede yüzlerce deney çalıştırıp, insanın aylar boyunca bulamayacağı iyileştirmeleri keşfedebiliyorlar. Ve bu bulgular küçük modelden büyük modele transfer ediliyor.
