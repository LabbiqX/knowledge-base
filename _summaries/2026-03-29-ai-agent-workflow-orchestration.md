---
layout: summary
title: "AI Agent Workflow Orchestration Guidelines"
date: 2026-03-29
source: "https://gist.github.com/OmerFarukOruc/a02a5883e27b5b52ce740cadae0e4d60"
category: "Multi-Agent Systems"
type: "GitHub"
---

## TL;DR
AI coding agent'larının gerçek bir codebase'de nasıl planlama, uygulama, doğrulama, iletişim ve hata kurtarma yapması gerektiğini tanımlayan kapsamlı bir kural seti. Doğruluk, minimalizm ve geliştirici deneyimi optimize edilmelidir. Subagent kullanımı, artımlı geliştirme, öğrenme günlüğü ve güvenlik prensipleri içeriyor.

---

## Key Points
- **Temel prensipler:** Doğruluk > zekilik, en küçük değişiklik, mevcut pattern'leri kullan, kanıtla
- **Plan modu:** 3+ adım, çoklu dosya, mimari karar veya production etkisi varsa zorunlu
- **Subagent kullanımı:** repo keşfi, test failure triage, bağımlılık araştırması — her birine tek odaklı görev ver
- **İnce dikey dilimler:** implement → test → verify → genişlet döngüsü
- **Ders günlüğü:** tasks/lessons.md'ye hata modu, tespit sinyali ve önleme kuralı kaydet
- **Tamamlanma kriteri:** testler geçiyor, lint/typecheck/build geçiyor, mevcut convention'lar takip ediliyor
- **Hata ayıklama:** reproduce → isolate → fix → regression coverage → verify
- **Güvenlik:** en az yetki, input validasyon, gizli bilgi kodda/log'da asla bulunmasın
- **İletişim:** sonuç ve etki ile başla, somut artifact referans ver, her checkpoint'te ne çalıştırıldığını belirt

---

## 🎯 Anahtar Çıkarım
> Bu, AI coding agent'ları için "staff engineer seviyesinde" davranış kılavuzu — doğruluk, minimalizm, sürekli öğrenme ve güvenlik odaklı, gerçek dünya codebase'lerine uygun sistematik bir yaklaşım.
