---
layout: summary
title: "Six Lessons Learned Building RAG Systems in Production"
date: 2026-03-29
source: "https://towardsdatascience.com/six-lessons-learned-building-rag-systems-in-production/"
category: "RAG & Knowledge"
type: "Makale"
---

## TL;DR
Kötü RAG sistemi, RAG olmamasından daha kötü — yanlış cevaplar güvenle verildiğinde kullanıcı güveni bir daha geri gelmez. 6 ders: gerçek iş problemiyle başla, veri hazırlığı beklenenden uzun sürer, chunking fikir bütünlüğünü korumalı, veriler eskiyecek, eval olmadan hatalar sadece şikayetle ortaya çıkar, trendy mimariler genelde gereksiz.

---

## 6 Ders

### 1. Gerçek İş Problemiyle Başla
- "Herkes yapıyor" strateji değil
- "Dahili soruları yanıtla" use case değil — spesifik ol (HR politika soruları, onboarding asistanı)
- ROI ölçülemiyorsa proje olmamalı
- **Kural:** Trend takip etme, değer uygula

### 2. Veri Hazırlığı Beklenenden Uzun Sürer
- Hızlı MVP mümkün ama production farklı — gerçek veriyle zayıflıklar ortaya çıkar
- Büyük context window RAG'in yerine geçmiyor (maliyet, latency, karmaşıklık)
- Ham veriyi direkt VectorDB'ye atmak = cosine similarity sandbox'u
- **Olgun RAG:** Veri hazırlığının kendi pipeline'ı, testleri ve versiyonlaması var
- GIGO (Garbage In, Garbage Out) hala geçerli

### 3. Chunking = Fikir Bütünlüğünü Koru
- Token/karakter limiti ile kırma → fragman, drift, güvenilmezlik
- **Semantic Chunking:** Her chunk tek bütün fikir
- Yöntemler: Recursive splitting (başlık → paragraf → cümle), sentence transformer tabanlı segmentasyon
- Başka şirketin chunking stratejisini kendi verinizi anlamadan kopyalamak tehlikeli

### 4. Veriler Eskiyecek
- Embedding'ler güncellenmezse model "tarihsel kayıtlardan hallucinate" eder
- VectorDB güncelleme teknik olarak zor: re-chunk, yeni vektör üret, eskisini sil/değiştir
- **Embedding versioning:** Hangi doküman hangi embedding run ile oluşturuldu?
- Otomatik re-embed: major versiyon değişikliği, büyük regülasyon değişimi
- VectorDB migration çoğu takımın atladığı adım

### 5. Eval Olmadan Hatalar Sadece Şikayetle Çıkar
- RAG eval = klasik LLM eval'dan farklı — retrieval + generation ayrı değerlendirmeli
- **Multi-level eval:** Her bileşen ayrı + uçtan uca iş metrikleri
- Dev'den production'a her aşamada eval gerekli
- Eval olmadan POC'tan ölçülebilir projeye geçiş imkansız

### 6. Trendy Mimari Genelde Gereksiz
- **Basic RAG:** Basit, tekrarlayan sorgular → yeterli
- **Two-Step Query Rewriting:** Belirsiz/dolaylı kullanıcı inputu → sorguyu temizle
- **Agentic RAG:** Karmaşık akıl yürütme + tool kullanımı + iş akışı gerekiyorsa
- Çoğu iş problemi Basic veya Two-Step ile çözülür — "agentic" trendy ama genelde gereksiz

---

## 🎯 Anahtar Çıkarım
> RAG'in en büyük riski teknik değil, insani: güvenle verilen yanlış cevaplar güveni kalıcı olarak yok eder. Birkaç hatalı yanıt, kullanıcıları manuel aramaya geri gönderir ve sistem iyileşse bile kimse tekrar denemez. Bu yüzden evaluation ve veri kalitesi mimariden önce gelir.
