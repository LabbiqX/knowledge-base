---
layout: summary
title: "Continuous AI in Practice: What Developers Can Automate with Agentic CI"
date: 2026-03-29
source: "https://github.blog/ai-and-ml/generative-ai/continuous-ai-in-practice-what-developers-can-automate-today-with-agentic-ci/"
category: "AI Agent Architecture"
type: "GitHub"
---

## TL;DR
GitHub Next, "Continuous AI" konseptini tanıttı: repo'nuzda CI job'ları gibi çalışan ama yargı gerektiren görevleri yapan arka plan agent'ları. CI deterministik kurallarla çalışır (test geçti/geçmedi), Continuous AI ise doğal dil kuralları + agentic reasoning ile çalışır. Dokümantasyon-kod uyumsuzluğu, anlamsal regresyonlar, bağımlılık etki analizi gibi "intent-bağımlı" görevleri kapsar.

---

## Key Points
- **CI:** Deterministik kurallar (test, build, lint) → binary sonuçlar
- **Continuous AI:** Doğal dil kuralları + agentic reasoning → yargı gerektiren görevler
- **Safe Outputs:** Agent'lar varsayılan olarak read-only; PR, issue, comment oluşturma izni açıkça verilmeli
- **PR odaklı:** Agent'lar otonom commit yapmaz — PR oluşturur, geliştirici review eder
- **Pratik örnekler:** Dokümantasyon-kod uyumu, stil ihlalleri, performans regresyonları, anlamsal UI değişiklikleri
- **Pattern:** Agentic workflow yaz → GitHub Action'a derle → push et → tetikleyicilerde çalışsın
- **YAML tamamlayıcısı:** Doğal dil YAML'ı değiştirmiyor, belirlenemeyen kuralları kapsıyor
- GitHub Next prototipi: `gh aw` CLI ile kullanılabilir

---

## 🎯 Anahtar Çıkarım
> Continuous AI, CI'ın "kural tabanlı" otomasyonunu "yargı gerektiren" görevlere genişletiyor — doğal dil ile ifade edilen beklentiler, repo'da sürekli çalışan agent'lar tarafından değerlendirilir ve güvenli çıktılar (PR, issue) üretir.
