---
layout: summary
title: "The Era of \"AI as Text\" Is Over — Execution Is the New Interface"
date: 2026-03-29
source: "https://github.blog/ai-and-ml/github-copilot/the-era-of-ai-as-text-is-over-execution-is-the-new-interface/"
category: "AI Agent Architecture"
type: "GitHub"
---

## TL;DR
GitHub, AI'ı "metin gir-metin al" döneminden "programlanabilir execution" dönemine taşıyan Copilot SDK'yı tanıttı. SDK, GitHub Copilot CLI'daki planlama ve yürütme motorunu uygulamalara gömmeyi sağlıyor. Üç temel pattern: çok adımlı işleri agent'a devretme, MCP ile yapılandırılmış runtime context, ve IDE dışına (masaüstü, SaaS, arka plan servisleri) execution yayma.

---

## Key Points
- **Pattern 1:** Intent delege et, sabit adımlar kodlama — agent repo keşfi, dosya düzenleme, hata kurtarma yapar
- **Pattern 2:** Prompt'a context doldurma yerine MCP ile yapılandırılmış, izinli runtime context sağla
- **Pattern 3:** Execution'ı IDE dışına çıkar — masaüstü, SaaS, event-driven sistemlere göm
- Copilot SDK: production-tested orchestration engine'i programlanabilir katman olarak sunar
- "AI as execution" mimari bir kayma: planlama + yürütme döngüleri kısıtlamalar altında çalışır
- MCP agent'ları gerçek araç ve verilere bağlıyor — prompt tabanlı tahmin yerine

---

## 🎯 Anahtar Çıkarım
> AI'ın arayüzü artık metin değil, yürütme — Copilot SDK ile uygulamalar agent'ları programatik olarak çağırabilir ve "eğer mantık tetikleyebiliyorsanız, agent execution tetikleyebilirsiniz" prensibi geçerli.
