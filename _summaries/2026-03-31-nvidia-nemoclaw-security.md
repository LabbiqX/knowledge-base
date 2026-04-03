---
layout: summary
title: "Nvidia NemoClaw: Agent Güvenliğinin Üç Katmanı (ve Hâlâ Çözülmeyen Asıl Problem)"
date: 2026-03-31
source: "https://thenewstack.io/nvidia-nemoclaw-openclaw-security/"
category: "AI Safety & Security"
type: "Makale"
---

## TL;DR
Nvidia, agentic computing talebindeki 10.000x artışa yanıt olarak OpenClaw üzerine NemoClaw güvenlik katmanı çıkardı. Üç bileşen: policy enforcement, privacy routing, audit trail. Ancak makale bunların hiçbirinin temel sorunu çözmediğini argüman ediyor — otonom agent'ları kısıtlamak inherent olarak verimsiz.

## Detaylı Özet

### Bağlam
- GTC'de Jensen Huang: 2 yılda **kullanıcı başına 10.000x compute talep artışı**, genel kullanım 100x
- OpenClaw kişisel kullanımda en popüler agentic platform
- Nvidia OpenClaw'ı tam destekliyor — en kısıtlamasız token kullanım formu

### NemoClaw'un Üç Güvenlik Katmanı

**1. Policy Enforcement (Politika Uygulaması)**
- Dosya sistemi ve ağ erişimini kısıtlama
- Agent engellenmişse neden engellendiğini anlayıp politika güncelleme önerebilir
- **Eleştiri:** "Yatak odasının penceresinden çıkarsa seni tamamen bypass eder"
- Daha fazla skill = daha az etkili politika — sadece geçmişten öğrenir
- İkilem: ya sürekli dur deyip otonomiyi öldür, ya da 7/24 çalışan bir zekaya karşı tahminde bulun

**2. Privacy Routing**
- Nelerin lokalde kalacağı, nelerin bulut modellere gideceğini belirle
- Maliyet kontrolü + IP koruma
- **Eleştiri:** Agent'ın üçüncü taraf isteğiyle şifreleri mail atmasını engellemez

**3. Audit Trail**
- (Makaleden tam detay alınamadı — truncated)

### Temel Argüman
> "Kendini geliştiren agent'ların paket yüklemesine, skill öğrenmesine, subagent spawn'lamasına izin verip sonra kapıda durdurmak inherent olarak verimsiz."

- Başarı, mühendislerin **deneyim ve sinizminden** bağlı
- NemoClaw OpenClaw'ın **yerine geçmiyor**, üstüne oturuyor

### Pazar Dinamiği
- Nvidia'nın motivasyonu: daha fazla token kullanımı = daha fazla GPU satışı
- Anthropic gibi Nvidia da "OpenClaw'dan sizi OpenClaw'a karşı koruyacağız" diyor
- Güvenlik katmanı ekleme stratejisi Anthropic ile paralel

## 🎯 Anahtar Çıkarım
Agent güvenliği hâlâ çözülmemiş problem. Policy-based yaklaşımlar reaktif — agent yeni bir yol bulduğunda geride kalıyor. NemoClaw'un gerçek değeri privacy routing (maliyet + IP koruma) olabilir, ama otonomiye karşı güvenlik trade-off'u fundamental. "Otonom agent + tam güvenlik" bir oksimoron olabilir — gerçek çözüm muhtemelen agentic mimarinin kendisinde, guardrail katmanında değil.
