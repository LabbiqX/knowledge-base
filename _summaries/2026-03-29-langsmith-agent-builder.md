---
layout: summary
title: "LangSmith Agent Builder — Public Beta"
date: 2026-03-29
source: "https://blog.langchain.com/langsmith-agent-builder-now-in-public-beta/"
category: "AI Agent Architecture"
type: "Makale"
---

## TL;DR
LangChain, kodsuz agent oluşturma aracı LangSmith Agent Builder'ı public beta'ya açtı. Geleneksel if-this-then-that iş akışı oluşturucularının aksine, gerçek agent'lar oluşturuyor — adımları kendisi belirleyen, araçları döngüde çağıran, geri bildirimle öğrenen. Chat tabanlı arayüzle birkaç dakikada agent kurulumu mümkün. MCP ile harici API bağlantısı, workspace şablonları ve multi-model desteği eklendi.

---

## Geleneksel Workflow Builder vs Agent Builder
| Workflow | Agent |
|----------|-------|
| Sabit yol, adım adım tanımlı | Dinamik, kendi adımlarını belirler |
| Edge case'leri önceden düşünmen lazım | Yeni bilgiye adapte olur |
| Belirli akış | İş bitene kadar araç çağırır (döngü) |

## Yeni Beta Özellikleri
- **Kendi araçlarını getir (MCP):** Harici API'ler ve dahili sistemler MCP server üzerinden bağlanıyor
- **Workspace agent'ları:** Takım genelinde browse, copy, customize — tek tıkla klonlama
- **Multi-model:** OpenAI ve Anthropic modelleri arasında seçim
- **Programmatic API:** Agent'ları mevcut iş akışlarına entegre etme
- **Basitleştirilmiş UI:** LangSmith içinde ayrı tab

## Kullanım Örnekleri
- **Satış:** Günlük müşteri araştırma raporu — takvim, katılımcılar, haberler, geçmiş notlar
- **Pazarlama:** Haftalık rakip takibi — haberler, duyurular, lansman bilgileri
- **İşe alım:** Günlük aday taraması + önceliklendirme + outbound mesaj taslağı
- **Ürün/Mühendislik:** Slack'ten Linear issue oluşturma — kapsam, öncelik, sahip otomatik doldurma
- **E-posta:** Okuma, etiketleme, önceliklendirme, yanıt taslağı
- **Takvim:** Odak zamanı koruma — toplantı eşiği aşılınca blok koyma

## Çalışma Prensibi
- Yönetici gibi çalışıyorsun, programcı gibi değil
- Ne istediğini anlat, araçları onayla, agent yaklaşımı kendi belirlesin
- Doğal dille güncelleme — iş akışını yeniden kurmaya gerek yok
- Uzun süreli hafıza ile geri bildirimden öğrenme

---

## 🎯 Anahtar Çıkarım
> No-code agent builder'lar "iş akışı tanımla" modelinden "ne istediğini söyle" modeline geçiyor. LangSmith'in yaklaşımı — chat ile agent oluşturma, MCP ile araç bağlama, uzun süreli hafıza ile öğrenme — agent demokratikleşmesinin bir sonraki adımı. Teknik olmayan ekipler için güçlü ama kurumsal güvenlik gereksinimleri için workspace/MCP kontrol katmanı mevcut.
