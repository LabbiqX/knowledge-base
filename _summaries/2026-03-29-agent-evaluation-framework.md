---
layout: summary
title: "Agent Evaluation: How to Test and Measure Agentic AI Performance"
date: 2026-03-29
source: "https://machinelearningmastery.com/agent-evaluation-how-to-test-and-measure-agentic-ai-performance/"
category: "Agent Evaluation"
type: "Makale"
---

## TL;DR
Agent değerlendirmesi, geleneksel LLM metriklerinden (BLEU, perplexity) temelden farklıdır. Dört sütun: görev başarısı, araç kullanım kalitesi, muhakeme tutarlılığı ve maliyet-performans dengesi. Üç değerlendirme yaklaşımı: LLM-as-Judge (otomatik, ölçeklenebilir), insan değerlendirmesi (pahalı ama edge case'leri yakalar) ve hibrit (ikisinin kombinasyonu).

---

## Key Points
- **Görev Başarısı:** Sonuç tabanlı, süreç tabanlı veya kalite tabanlı ölçüm
- **Araç Kullanım Kalitesi:** Relevance, accuracy, efficiency, completeness hataları
- **Muhakeme Tutarlılığı:** Ara adımlar mantıklı mı, alternatifler düşünüldü mü, yeni bilgiyle güncelleme yapıldı mı
- **Maliyet-Performans:** Token, API çağrısı, gecikme vs. sağlanan değer
- **LLM-as-Judge:** Hızlı, tutarlı ama grade inflation/deflation riski
- **İnsan Değerlendirmesi:** $10-50/görev, saatler-günler, edge case ve domain uzmanlığı için
- **Hibrit:** Otomatik filtre + yüksek önemli case'lerde insan review
- Benchmark'lar: AgentBench, WebArena, GAIA

---

## 🎯 Anahtar Çıkarım
> Agent değerlendirmesi, "doğru metin üretildi mi?" değil "görev doğru, verimli ve güvenilir şekilde tamamlandı mı?" sorusunu cevaplamalı — dört sütunlu framework ile üretim hazırlığı sistematik olarak ölçülebilir.
