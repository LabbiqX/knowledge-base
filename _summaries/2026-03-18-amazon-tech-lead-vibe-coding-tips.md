---
layout: summary
title: "Amazon Tech Lead'inden Vibe Coding İpuçları"
date: 2026-03-18
source: "https://www.businessinsider.com/amazon-tech-lead-promotion-vibecoding-tips-ai-products-2026-3"
category: "Vibe Coding"
type: "Makale"
---

## TL;DR
Amazon'da giriş seviyesinden kıdemli mühendisliğe terfi eden Anni Chen, kodunun **%95'ini AI ile yazıyor** ama farkı yaratan şey AI çıktısını ölçeklenebilir ürüne dönüştürmek. 4 temel ipucu: LLM'in iç işleyişini anla (nerede başarısız olacağını bil), **önce kendin düşün sonra AI'a sor**, zor soruları sor (hata durumu, ölçekleme), ve **her adımda review et** — sonunda toplu değil. Yanlış kod, kod yokluğundan daha tehlikeli.

---

## Arka Plan
- 2022'de Amazon'a giriş seviyesinde başladı
- Yan proje olarak AI ürünleri geliştirmeye başladı → kendi takımına dönüştü
- Şimdi Amazon'da generatif AI deneyimlerinde **memory/personalization** üzerine çalışıyor
- Kodunun %95'i AI tarafından yazılıyor

## 4 Vibe Coding İpucu

### 1. LLM'in İç İşleyişini Anla
- **Pre-training → SFT → RLHF** — bu 3 adımı bilirsen nerede başarısız olacağını anlarsın
- Context window sınırını bilirsen problemi ne zaman parçalaman gerektiğini anlarsın
- Detay vermezsen LLM en yaygın pattern'e varsayılan yapar — ama senin use case'in farklı olabilir
- LLM'e **bir meslektaşına açıklar gibi** açıkla

### 2. Önce Kendin Düşün, Sonra AI'a Sor
- Cevabı önce görürsen düşüncen cevaba doğru kayar
- Kendi düşünceni oluştur → AI'ın cevabıyla karşılaştır → farkları analiz et
- Fark = AI'a söylemediğin implicit varsayımlar

### 3. Zor Soruları Sor
- "Hata olduğunda fallback ne?"
- "Bu nasıl ölçeklenecek?"
- Kıdemli mühendis → junior mühendis gibi sorgula
- Ölçeklemeyi 1. günden düşün

### 4. Her Adımda Review Et
- Tüm kod üretildikten sonra değil, **her adımda** kontrol et
- Hataları erken durdur — kaskat hata yayılmasını önle
- ⚠️ **Yanlış kod, kod yokluğundan daha tehlikeli** — çalışıyor gibi göründüğü için insanlar güvenir

## Kodu Anlamak Hâlâ Zorunlu
- AI yazma bariyerini düşürüyor ama **sorumluluğu düşürmüyor**
- Production'da patlayan kodu "AI yazdı, ben de bilmiyorum" diye açıklayamazsın
- Öğrenme fırsatı: AI'a konsepti **ayrı bir pencerede** açıklattır (aynı pencerede sorarsan sadece o bağlamda açıklar)

---

## 🎯 Anahtar Çıkarım
> AI ile kodlamanın sırrı kodun kendisi değil — **AI çıktısını anlayarak ölçeklenebilir ürüne dönüştürmek.** Önce kendin düşün, her adımda review et, zor soruları sor. Yanlış çalışan kod, hiç olmayan koddan daha tehlikeli.
