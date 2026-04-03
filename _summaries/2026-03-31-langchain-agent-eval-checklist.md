---
layout: summary
title: "LangChain: Agent Evaluation Readiness Checklist"
date: 2026-03-31
source: "https://blog.langchain.com/agent-evaluation-readiness-checklist/"
category: "Agent Evaluation"
type: "Makale"
---

## TL;DR
LangChain'den pratik bir agent eval rehberi. En basit eval ile başla, gerçek trace'leri oku, hata analizi yaparak %60-80 çabayı buraya harca. Üç seviye: single-step (run), full-turn (trace), multi-turn (thread). En önemli mesaj: "state change eval'i ihmal etme — agent 'Done!' diyebilir ama gerçekte bir şey yapmamış olabilir."

## Detaylı Özet

### Eval Öncesi Yapılacaklar
1. **20-50 gerçek trace'i elle incele** — otomatik altyapı kurmadan önce
2. **Kesin başarı kriteri tanımla** — iki uzman pass/fail konusunda anlaşamıyorsa görev bozuk
3. **Capability vs Regression eval'i ayır:**
   - Capability: "Ne yapabiliyor?" — düşük pass rate'le başla, gelişimi ölç
   - Regression: "Hâlâ çalışıyor mu?" — ~%100 pass rate beklenir
4. **Hatanın nedenini açıklayabilmen gerekir** — açıklayamıyorsan daha fazla hata analizi yap
5. **Eval sahipliği tek bir domain uzmanına verilmeli**
6. **Altyapı sorunlarını agent'ı suçlamadan önce ele al** — Witan Labs: tek bir extraction bug %50→%73 fark yarattı

### Üç Eval Seviyesi

| Seviye | Ne test eder? | Ne zaman? |
|--------|--------------|-----------|
| **Single-step (Run)** | Doğru tool seçildi mi? Geçerli API çağrısı mı? | Stabil mimari sonrası |
| **Full-turn (Trace)** | Son yanıt doğru mu? Yol mantıklı mı? State değişti mi? | **İlk başlanacak yer** |
| **Multi-turn (Thread)** | Bağlam korunuyor mu? Çok turlu tutarlılık? | Trace eval sağlam olduktan sonra |

### State Change Evaluation (Kritik)
- Agent "Toplantı planlandı!" diyebilir ama takvimde etkinlik yoktur
- Kod yazdıysa → kodu çalıştır
- Veritabanı güncellediyse → satırları sorgula
- Dosya yazdıysa → dosyayı kontrol et

### Dataset Oluşturma
- Her görev **net ve çözülebilir** olmalı — referans çözüm ile birlikte
- **Pozitif VE negatif** vakalar test et (sadece "araması gereken" değil, "aramaması gereken" de)
- **N-1 testi:** Gerçek konuşma prefix'ini al, sadece son turu üret
- Trace→dataset flywheel kur: sürekli iyileştirme döngüsü

### Hata Analizi Framework'ü
1. Trace'leri topla → 2. Açık kodlama (kategorisiz not al) → 3. Kategorize et → 4. Yeni kategori çıkmayınca dur

**Hata kök nedenleri:**
- Prompt problemi → prompt'u düzelt
- Tool tasarım problemi → parametre/arayüz yeniden tasarla
- Model limitasyonu → mimari değiştir veya başka model dene
- Henüz belirsiz → daha fazla analiz

## 🎯 Anahtar Çıkarım
Agent eval'de en büyük hata: çok erken otomasyon, çok az hata analizi. Çabanın %60-80'i **neden başarısız olduğunu anlamaya** harcanmalı. "State change eval" çoğu ekibin kaçırdığı kritik nokta — agent "yaptım" demesi yetmez, gerçekten yaptığını doğrula. Basit full-turn eval ile başla, karmaşıklığı kanıta dayalı ekle.
