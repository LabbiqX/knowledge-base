---
layout: summary
title: "Kensho: LangGraph ile Multi-Agent Finansal Veri Erişimi"
date: 2026-03-31
source: "https://blog.langchain.com/customers-kensho/"
category: "Multi-Agent Systems"
type: "Makale"
---

## TL;DR
S&P Global'ın AI inovasyon motoru Kensho, parçalı finansal veri erişimini birleştirmek için LangGraph tabanlı multi-agent "Grounding" framework'ü geliştirdi. Router agent sorguları özelleşmiş Data Retrieval Agent'lara (DRA) yönlendiriyor, sonuçları birleştirip güvenilir yanıtlar sunuyor.

## Detaylı Özet

### Sorun
- Finansal profesyoneller dağınık sistemlerde veri arayarak saatler harcıyor
- Karmaşık veritabanı şemaları ve sorgu dilleri engel
- S&P Global verisi yüksek yapılandırılmış ve nüanslı — web araması gibi düz metin değil

### Grounding Mimarisi
```
Kullanıcı sorgusu → Router (LangGraph) → DRA'lara yönlendirme
                                         ├── Equity Research DRA
                                         ├── Fixed Income DRA
                                         ├── Macroeconomics DRA
                                         └── ...
                    → Aggregation Layer → Birleştirilmiş yanıt
```

**Router sorumlulukları:**
- Sorguyu bağlama göre doğru DRA'lara yönlendirme
- Sorguyu DRA-spesifik alt sorgulara bölme (map)
- Dağıtık yanıtları birleştirme (reduce)

**DRA'lar:**
- Tek sorumluluk prensibi — her DRA bir veri alanına özel
- Sinyal/gürültü oranını artırma
- Farklı veri takımlarınca sahiplenme (parallel ownership)

### Özel DRA Protokolü
- Tutarlı veri formatı (yapılandırılmış + yapılandırılmamış)
- Tüm agent ekosisteminde ortak iletişim arayüzü
- Yeni agent'lar anında tüm S&P Global verisine erişebiliyor

### LangGraph'ın Rolü
- Router grafının motoru
- Lokal iterasyon ve test kolaylığı
- Tek giriş noktası sağlama

### Öğrenilen Dersler
1. **Observability:** Kapsamlı tracing + metadata zorunlu — LangGraph native entegrasyonu kritik
2. **Çok aşamalı değerlendirme:** Routing kararları, veri kalitesi, yanıt tamlığı ayrı ayrı ölçülmeli (exact-match + tool-calling metrikleri)
3. **Protokol optimizasyonu:** Kullanıcı-agent etkileşim pattern'lerini analiz edip protokolü iteratif iyileştirme

### Ürünleştirme
- Equity research asistanı, ESG compliance agent'ı gibi ürünler aynı veri katmanı üzerinde
- Ortak altyapı → hızlı time-to-market

## 🎯 Anahtar Çıkarım
Kensho örneği, multi-agent sistemlerde **router + specialized agent** pattern'inin gerçek enterprise ölçeğinde çalıştığını gösteriyor. Kritik tasarım kararları: (1) ortak protokol ile agent'lar arası tutarlılık, (2) map-reduce ile dağıtık sorgulama, (3) her DRA'nın tek alana odaklanması. Observability ve çok aşamalı eval olmadan production'da başarı mümkün değil.
