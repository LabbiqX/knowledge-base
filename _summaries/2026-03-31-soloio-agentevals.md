---
layout: summary
title: "Solo.io AgentEvals: Agentic AI'ın En Büyük Çözülmemiş Problemi"
date: 2026-03-31
source: "https://thenewstack.io/soloio-agentevals-evaluates-ai-agents/"
category: "Agent Evaluation"
type: "Makale"
---

## TL;DR
Solo.io, KubeCon Europe'da agent'ları değerlendirmek için açık kaynaklı "agentevals" framework'ünü duyurdu. Altyapı otomasyonu, API orkestrasyonu ve servis yönetimi gibi gerçek dünya workflow'larında agent'ların güvenilirliğini, gecikmesini ve başarı oranını ölçüyor.

## Detaylı Özet

### Sorun
- Agent'ları oluşturma, bağlama ve yönetme framework'leri var — ama **güvenilirlik ölçümü yok**
- Kuruluşlar agent'ın production'da gerçekten güvenilir olup olmadığını bilemiyor
- CEO Idit Levine: "Evaluation, agentic altyapının bugün en büyük çözülmemiş problemi"

### AgentEvals Yapısı
- **Gerçek dünya workflow simülasyonu:**
  - Microservice konfigürasyonu
  - Routing policy güncelleme
  - Kubernetes cluster troubleshooting
- **Kontrollü koşullarda** çok adımlı görevleri simüle etme
- **Tekrarlanabilir** loglar, metrikler ve sonuç verileri
- Farklı AI backend'leri veya agent mimarileri karşılaştırılabilir

### Teknik Entegrasyonlar
- **Gloo Platform + Envoy Proxy** ile entegre
- **OpenTelemetry** tabanlı metrik toplama
- Ticari API'ler ve açık LLM'ler (Llama 3 vb.) için şeffaf metrikler
- Apache 2.0 lisansı

### CNCF Agent Registry
- KubeCon'da ayrıca CNCF'e agent registry bağışı da duyuruldu
- Cloud-native ekosistemde agent'ların standart kaydı ve yönetimi

## 🎯 Anahtar Çıkarım
AgentEvals, "agent'ı build ettik ama gerçekten çalışıyor mu?" sorusuna sistematik cevap arayan ilk cloud-native odaklı açık kaynak framework. OpenTelemetry entegrasyonu observability ile eval'i birleştiriyor — LangChain'in eval yaklaşımıyla (trace→eval) paralel bir trend. Evaluation standardizasyonunun cloud-native ekosistemden gelmesi, agent'ların artık "oyuncak" değil "altyapı" olarak görüldüğünün kanıtı.
