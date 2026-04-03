---
layout: summary
title: "Why Notion's Biggest AI Breakthrough Came from Simplifying Everything"
date: 2026-03-29
source: "https://venturebeat.com/infrastructure/why-notions-biggest-ai-breakthrough-came-from-simplifying-everything"
category: "AI Agent Architecture"
type: "Makale"
---

## TL;DR
Notion AI ekibi ilk başta karmaşık kod üretimi, complex schema ve ağır talimatlar kullandı — sonra hepsini attı. Basit prompt'lar, markdown formatı, minimal araç seti ve 100K-150K token "sweet spot" ile dramatik performans artışı elde etti. V3'te customizable AI agent'lar çıktı — Notion'ın en başarılı AI özelliği.

---

## Temel Dersler
- **İnsana anlatır gibi yaz:** "Bağlamsız birine versem anlayabilir mi?" — anlayamazsa model de kötü iş çıkaracak
- **Markdown > JSON/XML:** LLM plain text'i daha iyi anlıyor, Notion sayfalarını markdown olarak temsil et
- **Context window disiplini:** 100K-150K token sweet spot — daha fazlası latency, doğruluk ve performans düşürüyor
- **Minimal araç seti:** Her talep için araç ekleme — model ne kadar çok araç görürse o kadar çok karar vermek zorunda
- **"Curated menu" > "Cheesecake Factory menu":** Paradox of choice
- **Erken aşamada maliyet optimizasyonu yapma** — sonra optimize et

## Notion'ın Evrimi
- Karmaşık data modelleme → basit prompt + markdown
- Middleware transition layer'a odaklanma
- V3: Customizable AI agents — "step function improvement"
- "Ürün sizden çekiliyor, siz itmeye çalışmıyorsunuz"

---

## 🎯 Anahtar Çıkarım
> AI mühendisliğinin paradoksu: daha az karmaşıklık = daha iyi performans. Notion'ın deneyimi "insana anlatır gibi yaz, markdown kullan, araç sayısını minimize et" kuralıyla özetlenebilir. Geleneksel yazılım mühendisliği alışkanlıkları (abstraction, complex schema) LLM'lerle çalışırken genelde zararlı.
