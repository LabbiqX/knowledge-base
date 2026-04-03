---
layout: summary
title: "Clawdbot Nedir? Clawdbot Nasıl Kurulur?"
date: 2026-03-29
source: "https://shiftdelete.net/clawdbot-nedir-clawdbot-nasil-kurulur"
category: "AI Agent Architecture"
type: "Makale"
---

## TL;DR
ShiftDelete.net, Clawdbot (OpenClaw tabanlı) açık kaynaklı AI asistanının Türkçe kurulum rehberini yayınladı. Node.js gerektiren sistem Windows, macOS ve Linux'ta kurulabiliyor. Discord, Telegram, WhatsApp gibi kanallarla entegre çalışıyor. API sağlayıcı olarak Anthropic, OpenAI veya Vercel AI Gateway seçilebiliyor. E-posta yönetimi, toplantı planlama, web araştırması gibi görevleri 7/24 otonom yapabiliyor.

---

## Key Points
- Node.js v22+ gerekli; Windows (PowerShell), macOS (Homebrew/script), Linux (npm) kurulum seçenekleri
- `clawdbot onboard --install-daemon` ile kurulum sihirbazı
- API seçenekleri: Anthropic (Claude), OpenAI, Vercel AI Gateway
- Kanal desteği: Discord, Telegram, WhatsApp
- Temel komutlar: onboard, gateway, doctor, update, logs
- Güvenlik: halka açık sunucularda `dmPolicy: "pairing"` ile erişim kısıtlama
- Google Drive, Gmail entegrasyonu; Brave arama motoru bağlantısı
- AWS ücretsiz sunucu + Ubuntu ile 7/24 çalışma önerisi

---

## 🎯 Anahtar Çıkarım
> Clawdbot, teknik olmayan kullanıcıların bile "kopyala-yapıştır" yöntemiyle kendi AI asistanını kurabileceği açık kaynaklı bir araç — Türkçe kurulum rehberi sayesinde Türk kullanıcı tabanına erişiyor.
