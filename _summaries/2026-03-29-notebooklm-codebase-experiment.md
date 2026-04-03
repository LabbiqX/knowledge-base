---
layout: summary
title: "I Fed My Entire Codebase into NotebookLM and It Became My Best Junior Developer"
date: 2026-03-29
source: "https://www.xda-developers.com/entire-codebase-in-notebooklm-experiment/"
category: "AI Agent Architecture"
type: "Makale"
---

## TL;DR
Bir geliştirici, küçük bir Python projesinin tüm kaynak kodunu NotebookLM'e yükleyerek onu bir "junior developer" gibi kullanmayı denedi. Sonuç: onboarding özeti, debugging yardımı, mimari sorular ve test gap analizi konularında beklenenden iyi performans. Küçük, stabil projeler için bağlamı bir kere yükleyip tekrar tekrar kullanmak zaman kazandırıyor.

---

## Key Points
- Tüm .py dosyaları, README ve klasör yapısı NotebookLM'e yüklendi
- "Junior developer" gibi sorular soruldu: sistem anlayışı, hata ayıklama, mimari bağımlılıklar
- NotebookLM, paylaşılan state sorunlarını ve tight coupling risklerini doğru tespit etti
- Sınırlılıklar: manuel güncelleme gerekli, büyük/hızlı değişen projeler için pratik değil
- Gizli projeler için uygun değil (veri dışa çıkıyor)
- En uygun kullanım: eski, küçük, nadiren değişen projeler

---

## 🎯 Anahtar Çıkarım
> NotebookLM, tam bağlam ile yüklendiğinde küçük projeler için etkili bir "ikinci beyin" olarak çalışıyor — düşünmeyi destekliyor, yerine koymuyor.
