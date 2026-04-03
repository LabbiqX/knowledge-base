---
layout: summary
title: "How We Built Agent Builder's Memory System"
date: 2026-03-29
source: "https://blog.langchain.com/how-we-built-agent-builders-memory-system/"
category: "RAG & Knowledge"
type: "Makale"
---

## TL;DR
LangSmith Agent Builder, no-code agent oluşturma platformu olarak hafıza sistemini ilk günden önceliklendirdi. Hafıza, dosya sistemi şeklinde temsil ediliyor (AGENTS.md, tools.json, skills, knowledge files) ve Postgres'te sanal dosya sistemi olarak saklanıyor. Agent, kullanıcı düzeltmelerinden öğrenerek AGENTS.md'yi iteratif olarak güncelliyor — upfront dokümantasyon yerine kullanım yoluyla "kendi kendini yazan" bir spec oluşuyor.

---

## Key Points
- Hafıza tipolojisi (COALA paper): Procedural (AGENTS.md, tools.json), Semantic (skills, knowledge files), Episodic (henüz yok)
- Dosya sistemi formatı: LLM'ler dosya sistemleriyle iyi çalıştığı için bu tercih yapıldı
- Gerçek dosya sistemi yerine Postgres + sanal dosya sistemi kullanılıyor (altyapı kolaylığı)
- AGENTS.md, kullanıcı düzeltmeleriyle haftalarca iteratif olarak zenginleşiyor
- Deep Agents harness: summarization, tool call offloading, planning gibi context engineering'i soyutluyor
- En zor kısım: prompting — hemen hemen tüm performans sorunları prompt iyileştirmesiyle çözüldü
- Endüstri standartları kullanımı: AGENTS.md, agent skills, MCP

---

## 🎯 Anahtar Çıkarım
> En etkili agent hafızası, kullanıcının açıkça yazdığı değil, agent'ın kullanım sürecinde düzeltmelerden öğrenerek iteratif olarak oluşturduğu hafızadır — dosya sistemi bu için doğal ve etkili bir araçtır.
