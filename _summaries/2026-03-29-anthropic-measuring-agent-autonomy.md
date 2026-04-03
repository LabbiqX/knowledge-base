---
layout: summary
title: "Measuring AI Agent Autonomy in Practice"
date: 2026-03-29
source: "https://www.anthropic.com/research/measuring-agent-autonomy"
category: "AI Agent Architecture"
type: "Makale"
---

## TL;DR
Anthropic milyonlarca insan-agent etkileşimini analiz etti. Bulgular: Claude Code'un en uzun çalışma süresi 3 ayda neredeyse ikiye katlandı (25dk → 45dk). Deneyimli kullanıcılar daha fazla auto-approve veriyor (%20 → %40+) ama daha sık müdahale ediyor. Claude Code, insanların müdahale etmesinden daha sık kendisi durup soru soruyor. Modellerin pratikte kullanılan otonomisi, kapasitelerinin gerisinde kalıyor — "deployment overhang" var.

---

## Temel Bulgular

### 1. Otonom Çalışma Süresi Artıyor
- 99.9. persentil turn süresi: 25dk → 45dk (3 ayda)
- Medyan: ~45 saniye (stabil)
- Artış model release'leriyle değil, kullanıcı güveni + araç iyileştirmesiyle
- Tatil dönüşü azalma: hobi projelerinden iş projelerine geçiş

### 2. Deneyim ve Otonomi İlişkisi
- Yeni kullanıcılar (<50 session): %20 auto-approve
- Deneyimli kullanıcılar (750+ session): %40+ auto-approve
- **Paradoks:** Daha fazla otonomi veren kullanıcılar daha sık müdahale ediyor
- Yorum: Deneyimli kullanıcılar ne zaman müdahale edileceğini biliyor

### 3. Agent Kendisi Duruyor
- Karmaşık görevlerde Claude Code insanlardan 2x daha sık durup soru soruyor
- Agent-initiated stops da bir denetim biçimi

### 4. Riskli Alanlar Artıyor Ama Küçük
- Agentic aktivitenin ~%50'si yazılım mühendisliği
- Sağlık, finans, siber güvenlik'te yükselen kullanım
- Çoğu agent eylemi düşük riskli ve geri dönülebilir

### 5. Deployment Overhang
- Modellerin kapasitesi > pratikte verilen otonomi
- METR değerlendirmesi: Opus 4.5 insan için 5 saatlik görevi %50 başarıyla tamamlıyor
- Pratikte 99.9. persentil ~42 dakika — kapasite kullanımı çok düşük

## Dahili Sonuçlar
- Anthropic'in iç kullanımı: başarı oranı 2x arttı, insan müdahalesi 5.4 → 3.3/session

## Öneriler
- Etkili denetim için yeni post-deployment monitoring altyapısı gerekli
- İnsan-AI etkileşim paradigmaları: otonomi ve riski birlikte yönetme

---

## 🎯 Anahtar Çıkarım
> "Deployment overhang" — modellerin kapasitesi pratikte kullanılanın çok önünde. En ilginç bulgu: deneyimli kullanıcılar daha fazla otonomi veriyor ama daha sık müdahale ediyor — bu "güven ama doğrula" yaklaşımının doğal sonucu. Agent denetimi statik kurallardan ziyade dinamik insan-AI etkileşim paradigmalarıyla çözülmeli.
