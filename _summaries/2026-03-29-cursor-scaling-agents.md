---
layout: summary
title: "Scaling Long-Running Autonomous Coding (Cursor)"
date: 2026-03-29
source: "https://cursor.com/blog/scaling-agents"
category: "AI Coding Tools"
type: "Makale"
---

## TL;DR
Cursor, yüzlerce eşzamanlı coding agent'ı haftalarca çalıştırarak 1M+ satır kod yazdırdı. Flat koordinasyon başarısız oldu — agent'lar risk-averse davrandı, lock'lar darboğaz yarattı. Planner-Worker ayrımı sorunu çözdü: planner'lar recursive olarak görev oluşturur, worker'lar sadece kendi görevine odaklanır. GPT-5.2 uzun süre otonom çalışmada en iyi model. En büyük ders: karmaşıklık ekleme değil çıkarma ile iyileşme geldi.

---

## Tek Agent'ın Sınırları
- Odaklı görevlerde iyi, karmaşık projelerde yavaş
- Doğal çözüm: paralel agent → ama koordinasyon zor

## Koordinasyon Deneyleri

### Başarısız: Flat Koordinasyon
- Eşit statüde agent'lar, paylaşılan dosyayla self-coordination
- Lock mekanizması: darboğaz, 20 agent → 2-3 agent throughput'u
- Agent'lar lock tutmayı unutur, fail eder, lock'suz yazar
- Optimistic concurrency: daha basit ama derin sorunlar devam
- **Hiyerarşi yoksa agent'lar risk-averse olur** — zor görevlerden kaçar, küçük güvenli değişiklikler yapar

### Başarılı: Planner-Worker Pipeline
- **Planner:** Codebase'i keşfeder, görev oluşturur, sub-planner spawn edebilir (recursive/paralel)
- **Worker:** Tek göreve odaklanır, tamamlayana kadar çalışır, push eder
- **Judge:** Her döngü sonunda devam kararı verir, sonraki iterasyon sıfırdan başlar
- Koordinasyon sorunlarını çözdü, tunnel vision'ı engelledi

## Sonuçlar
| Proje | Süre | Kod |
|-------|------|-----|
| Web browser (sıfırdan) | ~1 hafta | 1M+ satır, 1000 dosya |
| Solid→React migration (Cursor codebase) | 3+ hafta | +266K/-193K düzenleme |
| Video rendering Rust optimizasyonu | — | 25x hızlanma, production'a merge |
| Java LSP | devam | 7.4K commit, 550K LoC |
| Windows 7 emülatörü | devam | 14.6K commit, 1.2M LoC |
| Excel | devam | 12K commit, 1.6M LoC |

## Önemli Dersler
- **GPT-5.2** uzun otonom işlerde en iyi: talimat takibi, odak, drift'e direniş
- **Opus 4.5** erken durur, kısayol alır, kontrolü hızlı bırakır
- Farklı modeller farklı rollerde iyi: GPT-5.2 planner olarak Codex'ten bile iyi
- **Karmaşıklık çıkarma > ekleme** — Integrator rolü kaldırıldı, worker'lar çatışmaları kendileri çözdü
- **Prompt > harness + model** — koordinasyon, odak, patolojik davranış engelleme hep prompt'ta
- Doğru yapı seviyesi: çok az = çatışma/drift, çok fazla = kırılganlık

---

## 🎯 Anahtar Çıkarım
> Multi-agent coding ölçeklenebilir — ama flat koordinasyon çalışmaz. Planner-Worker hiyerarşisi + periyodik yeniden başlangıç + role-based model seçimi ile yüzlerce agent haftalarca aynı codebase üzerinde verimli çalışabiliyor. En büyük sürpriz: sistemin davranışının çoğu prompt'lara bağlı, mimari ikinci planda.
