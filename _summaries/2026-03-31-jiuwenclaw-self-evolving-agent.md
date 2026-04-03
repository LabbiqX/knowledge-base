---
layout: summary
title: "JiuwenClaw: Self-Evolving AI Agent for Task Management"
date: 2026-03-31
source: "https://www.marktechpost.com/2026/03/27/openjiuwen-community-releases-jiuwenclaw-a-self-evolving-ai-agent-for-task-management/"
category: "AI Agent Architecture"
type: "Makale"
---

## TL;DR
openJiuwen topluluğu, görevleri baştan sona yürütmeye odaklanan JiuwenClaw'u yayınladı. Sohbet yeteneği yerine sürekli yürütme kapasitesini ön plana çıkarıyor. Dört katmanlı mimari: giriş, yürütme, stabilite ve evrim.

## Detaylı Özet

### Temel Sorun
Çoğu AI agent sohbette zeki görünür ama gerçek dünya görevlerinde başarısız olur. Sorun model zekası değil, **sürdürülebilir yürütme kapasitesinin** eksikliği.

### Mimari Katmanlar

**1. Akıllı Görev Planlama**
- Görev kesintisi, araya ekleme, yeniden sıralama, kaldırma desteği
- Değişikliklere rağmen hedefe odaklanma
- Görünür, kontrol edilebilir yürütme süreci

**2. Hiyerarşik Hafıza Sistemi**
- 3 katmanlı: stabil kimlik → uzun vadeli arka plan → dinamik yörünge
- Kullanımla biriken ve iterasyon yapan hafıza
- Bağlamsal bütünlük: yapı vs ton düzeyinde düzenleme ayrımı

**3. Akıllı Bağlam İnceltme (Context Slimming)**
- Gereksiz bilgiyi otomatik sıkıştırma, anahtar bağlamı koruma
- Token patlaması önleme, maliyet düşürme
- Uzun süreli görevlerde stabilite

**4. Otonom Beceri Evrimi**
- Araç hatası veya kullanıcı düzeltmesi → otomatik log
- Kök neden analizi (RCA) → optimizasyon stratejisi
- Kapalı döngü: Yürütme → Başarısızlık → Öğrenme → Optimizasyon → Tekrar yürütme

### Gerçek Dünya Otomasyonu
- Yerel tarayıcı ortamını devralma (cookie, oturum, cache)
- CAPTCHA ve tekrarlı giriş atlatma
- "Temiz sandbox" yerine "gerçek iş ortamı" yaklaşımı

### Platform Desteği
- Huawei Celia, Telegram, WhatsApp, Feishu/Lark, Web
- Özel dağıtım (private deployment) desteği

## 🎯 Anahtar Çıkarım
JiuwenClaw'un en dikkat çekici özelliği **otonom beceri evrimi**: agent'ın kendi hatalarından öğrenip kendini geliştirmesi. Bu, static agent'lardan self-evolving agent'lara geçişin somut bir örneği. Hiyerarşik hafıza sistemi (stabil/uzun vadeli/dinamik) OpenClaw'un kendi hafıza mimarisine benzer bir yaklaşım.
