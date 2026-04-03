---
layout: summary
title: "Demystifying Evals for AI Agents"
date: 2026-03-29
source: "https://www.anthropic.com/engineering/demystifying-evals-for-ai-agents"
category: "Agent Evaluation"
type: "Makale"
---

## TL;DR
Anthropic'in agent eval rehberi. Eval = agent'a input ver, output'u puanla. Agent eval'ları karmaşık çünkü agent'lar çok adımlı, araç kullanan, state değiştiren sistemler. Üç grader türü: code-based (hızlı, ucuz, deterministik), model-based (esnek, nuanslı), human (altın standart). Eval'sız takımlar "kör uçuş" yapıyor — yeni model çıktığında haftalarca test ederken eval'lı takımlar günlerde geçiyor.

---

## Eval Anatomisi
- **Task:** Tanımlı input + başarı kriterleri
- **Trial:** Bir task'ın tek denemesi (model çıktısı her seferinde değişir → birden fazla trial)
- **Grader:** Performansı puanlayan mantık (birden fazla grader + assertion olabilir)
- **Transcript/Trace:** Trial'ın tam kaydı — output, tool call, reasoning, ara sonuçlar
- **Outcome:** Ortamdaki son durum (agent "rezervasyon yapıldı" dedi, ama SQL'de var mı?)
- **Eval Harness:** Eval'ları uçtan uca çalıştıran altyapı
- **Agent Harness:** Modeli agent olarak çalıştıran sistem (ör. Claude Code)

## Üç Grader Türü

| Tür | Güçlü | Zayıf |
|-----|-------|-------|
| **Code-based** (string match, regex, unit test, static analysis) | Hızlı, ucuz, deterministik, debug kolay | Kırılgan, nüans yok |
| **Model-based** (rubric, pairwise comparison, multi-judge) | Esnek, nuanslı, açık uçlu görevlere uygun | Non-deterministik, pahalı, kalibrasyon lazım |
| **Human** (SME review, A/B test, spot-check) | Altın standart, model grader'ı kalibre eder | Pahalı, yavaş, ölçeklenmiyor |

## Capability vs Regression Eval
- **Capability:** "Agent bunu yapabiliyor mu?" — düşük pass rate ile başla, tırmanma hedefi
- **Regression:** "Agent hala yapabiliyor mu?" — ~%100 pass rate, gerileme kontrolü
- Yüksek pass rate'e ulaşan capability eval'lar → regression suite'e "mezun" olur

## Coding Agent Eval
- Deterministik grader'lar doğal: kod çalışıyor mu, testler geçiyor mu?
- SWE-bench Verified: GitHub issue → çözüm → test suite (1 yılda %40 → %80+)
- Transcript grading: araç kullanımı, kod kalitesi kuralları, model-based rubric
- Opus 4.5 örneği: τ2-bench'te "yanlış" cevap verdi ama aslında daha iyi çözüm buldu — eval sınırlaması

## Eval'ın Değeri
- Model yükseltme: eval'lı takımlar günlerde geçiyor, eval'sız haftalarca test ediyor
- Baseline + regression testi bedavaya gelir: latency, token, maliyet, hata oranı
- Product-research arasında en yüksek bandwidth iletişim kanalı
- Claude Code örneği: concision, file edits, over-engineering eval'ları ile iyileştirme

## Pratik Örnekler
- **Descript:** Video düzenleme agent'ı — "bozma, istediğimi yap, iyi yap" üç boyutlu eval
- **Bolt:** Scale'de eval sistemi — static analysis + browser agent test + LLM judge

---

## 🎯 Anahtar Çıkarım
> Eval'ların maliyeti önceden görünür, faydası birikimli. Eval'sız agent geliştirme başlangıçta hızlı görünür ama production'da "kör uçuş"a dönüşür. En önemli pratik: transcript (süreç) ve outcome (sonuç) ayrı değerlendirilmeli — agent doğru cevap verip yanlış yolla ulaşmış olabilir.
