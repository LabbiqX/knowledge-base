---
layout: summary
title: "Cloudflare: AST ile Workflow Kodunu Görsel Diyagramlara Dönüştürme"
date: 2026-03-31
source: "https://blog.cloudflare.com/workflow-diagrams/"
category: "AI Agent Architecture"
type: "Makale"
---

## TL;DR
Cloudflare, TypeScript ile yazılan Workflows kodunu otomatik görsel diyagramlara dönüştürüyor. Abstract Syntax Tree (AST) kullanarak Promise/await ilişkilerini analiz edip paralel ve sıralı adımları tespit ediyor. Coding agent'ların ürettiği kodu görselleştirme ihtiyacından doğmuş bir özellik.

## Detaylı Özet

### Motivasyon
- Coding agent'lar giderek daha fazla kod yazıyor — **kodun şekli hâlâ önemli**
- Adımların nasıl bağlandığı, nerede dallandığı görünür olmalı
- Deklaratif (JSON/YAML) sistemlerden farklı: Workflows **saf kod** — Promise, Promise.all, döngüler, koşullar içeriyor

### Dinamik Yürütme Modeli
- Cloudflare Workflows **dinamik yürütme** kullanıyor (sıralı değil)
- Adımlar runtime'da keşfediliyor, engine'e devrediliyor
- `await` edilmeyen adımlar **paralel** çalışıyor
- Engine bir "supervisor" Durable Object — adım sırasını bilmiyor

### AST Tabanlı Diyagram Üretimi
1. Deploy zamanında bundled script alınıyor
2. `oxc-parser` (JavaScript Oxidation Compiler) ile AST oluşturuluyor
3. Promise ve await ilişkileri izleniyor → paralel/sıralı ayrımı
4. Ara graf üretilip API'den diyagram render ediliyor

### Minified Kod Sorunu
- esbuild, rspack, vite gibi farklı bundler'lar farklı minification üretiyor
- Minified koddan doğru AST çıkarmak zor — OXC parser hız ve doğruluk dengesini sağlıyor

### Gerçek Dünya Örneği
- Agent'ların paralel çalışması: summary agent + correctness agent + clarity agent aynı anda
- Her biri ayrı `step.do()` çağrısı, await edilmeden paralel yürütme

## 🎯 Anahtar Çıkarım
Coding agent çağında **kod görselleştirme** kritik hale geliyor: agent'ın yazdığı kodu okumasan bile akış diyagramından ne yaptığını anlayabilirsin. Cloudflare'in AST yaklaşımı — saf kodu statik analiz ederek görsel grafa dönüştürmek — hem debug hem de güven açısından güçlü bir pattern. Ayrıca "await = sıralı, no-await = paralel" paradigması agent orkestrasyon tasarımına direkt uygulanabilir.
