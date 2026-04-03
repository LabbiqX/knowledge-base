---
layout: summary
title: "Developer's Guide to Multi-Agent Patterns in ADK"
date: 2026-03-29
source: "https://developers.googleblog.com/developers-guide-to-multi-agent-patterns-in-adk/"
category: "Multi-Agent Systems"
type: "Makale"
---

## TL;DR
Google'un Agent Development Kit (ADK) ile 8 multi-agent tasarım pattern'i rehberi. Monolitik agent'lar tıpkı monolitik uygulamalar gibi ölçeklenmiyor — karmaşıklık arttıkça hata oranı bileşik artıyor. Çözüm: microservices benzeri modüler, test edilebilir, uzmanlaşmış agent mimarisi. Her pattern ADK pseudocode ile açıklanmış.

---

## 8 Multi-Agent Pattern

### 1. Sequential Pipeline (Montaj Hattı)
- Agent A → Agent B → Agent C, doğrusal ve deterministik
- `output_key` ile paylaşılan state üzerinden veri aktarımı
- Kullanım: Veri işleme pipeline'ları (PDF parse → extract → özetle)

### 2. Coordinator/Dispatcher (Danışma)
- Merkezi agent kullanıcı niyetini analiz eder, uzman agent'a yönlendirir
- AutoFlow mekanizması: sub_agent description'larına göre otomatik routing
- Kullanım: Müşteri hizmetleri (fatura → BillingSpecialist, teknik sorun → TechSupport)

### 3. Parallel Fan-Out/Gather (Ahtapot)
- Bağımsız görevler eşzamanlı çalışır, sonuçlar toplanır
- Race condition önleme: her agent farklı output_key kullanmalı
- Kullanım: Kod review (güvenlik + stil + performans paralel → tek rapor)

### 4. Hierarchical Decomposition (Matruşka)
- Büyük görevler alt görevlere bölünür, AgentTool ile sub-agent fonksiyon gibi çağrılır
- Kullanım: Rapor yazımı (ReportWriter → ResearchAssistant → WebSearch + Summarizer)

### 5. Generator & Critic (Editör Masası)
- Üretim ve doğrulama ayrı: Generator → Critic → koşullu döngü
- Pass/Fail odaklı — doğruluk kontrolü
- Kullanım: SQL üretimi + syntax doğrulama

### 6. Iterative Refinement (Heykeltıraş)
- Generator → Critic → Refiner döngüsü, kalitatif iyileştirme
- max_iterations + erken çıkış (escalate=True)
- Generator&Critic'ten farkı: doğruluk değil kalite odaklı

### 7. Human-in-the-Loop (İnsan Güvenlik Ağı)
- Yüksek riskli aksiyonlarda insan onayı — geri dönüşü olmayan kararlar
- ApprovalTool ile execution duraklatma
- Kullanım: Finansal işlemler, production deployment, hassas veri aksiyonları

### 8. Composite Patterns (Karışık)
- Gerçek dünya: tek pattern yetmez, birleştir
- Örnek: Coordinator (routing) → Parallel (arama) → Generator+Critic (ton kontrolü)

## Pro Tips
- **State yönetimi kritik:** `output_key` açıklayıcı olsun
- **Description = API dokümantasyonu:** Routing için sub-agent description'ları net olmalı
- **Basit başla:** İlk gün nested loop kurma, sequential chain'den başla

---

## 🎯 Anahtar Çıkarım
> Multi-agent sistemler microservices gibi düşünülmeli: uzmanlaşma, modülerlik, test edilebilirlik. En önemli pratik kural "basit başla" — sequential chain debug et, sonra karmaşıklık ekle. State yönetimi ve agent description'ları sistemin sinir uçları.
