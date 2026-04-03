---
layout: summary
title: "Claude ile 24 Saatte Programlama Dili Yazmak: Elo"
date: 2026-03-29
source: "https://www.theregister.com/2026/01/24/human_ai_pair_programming_elo/"
category: "Anthropic & Claude"
type: "Makale"
---

## TL;DR
Belçikalı geliştirici Bernard Lambeau, Claude Code ile 24 saatte Elo adında tam bir programlama dili (parser, tip sistemi, 3 derleyici, stdlib, CLI, dokümantasyon sitesi) inşa etti. Claude Max aboneliği (€180/ay) ile "birkaç hafta sürecek" işi günlere sıkıştırdı. Anahtar: güçlü test metodolojisi — Claude testleri yazar, çalıştırır, hata bulur, düzeltir.

---

## Key Points
- 24 saatte: parser, type system, 3 compiler (JS, Ruby, SQL), stdlib, CLI, docs
- Claude Code: "full-stack++ dev" yapıyor — bilmediğin teknolojileri bile kullanabilirsin
- **Kritik başarı faktörü:** Test methodology — Claude test yazar, çalıştırır, hata bulur, düzeltir
- Güvenlik: izole ortam (Docker/ayrı Linux user) gerekli, otonom mod için
- CTO/Lead-dev + QA rolü: plan → test stratejisi → otonom mod → sonuç review
- €180/ay Claude Max ile: Elo dili + Bmg.js + docs + Try page — hepsi birkaç haftada
- "Expertise olmadan büyük bir bakımsız kod yığını elde edersin" — uzmanlar için amplifier
- Elo: non-Turing-complete, güvenli, basit — no-code araçlarında güvenli kod çalıştırma için

---

## 🎯 Anahtar Çıkarım
> AI pair programming'in gerçek gücü "her şeyi otomatik yazması" değil — güçlü test metodolojisi + uzman yönlendirmesi ile insan-AI ortaklığının üretkenliği 10x artırması.
