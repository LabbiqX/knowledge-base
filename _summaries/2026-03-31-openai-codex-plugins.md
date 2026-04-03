---
layout: summary
title: "OpenAI Codex'e Plugin Desteği Geldi"
date: 2026-03-31
source: "https://thenewstack.io/openais-codex-gets-plugins/"
category: "AI Coding Tools"
type: "Makale"
---

## TL;DR
OpenAI, Codex'e plugin sistemi ekledi. Plugin'ler MCP sunucuları, skill'ler ve uygulama entegrasyonlarını tek tıkla kurulabilir paketlere dönüştürüyor. Anthropic Claude Code ve Google Gemini CLI zaten benzer sistemlere sahipti — artık üç büyük vendor da aynı mimariyi kullanıyor.

## Detaylı Özet

### Plugin Yapısı
- **Skills** (Markdown tabanlı workflow'lar) + **App connector'lar** + **MCP sunucuları** tek pakette
- 20+ plugin ile lansman: Box, Figma, Linear, Notion, Sentry, Slack, Gmail, Hugging Face
- Codex app, CLI ve VS Code extension'da kullanılabilir

### Stratejik Anlam
- Codex'i "superapp"e dönüştürme hamlesi — sadece kodlama değil, planlama/araştırma/koordinasyon
- Plugin'ler kodlama öncesi ve sonrası aşamaları kapsıyor
- Takımlar arası standardizasyon: her geliştirici aynı plugin setini kullanabilir

### UI Entegrasyonu
- Codex UI'da özel "Plugins" sekmesi — 'New Thread' altında
- Küratörlü dizin, self-serve yayınlama yakında
- CLI'da `/plugins` komutu ile terminal'den kurulum

### Örnek: "Build Web App" Plugin
- Stripe + Supabase + Vercel MCP sunucuları
- Deploy, frontend build, web design best practice skill'leri tek pakette

### Vendor Karşılaştırma
| Vendor | Sistem Adı | Dağıtım |
|--------|-----------|---------|
| **Anthropic** Claude Code | Plugins | Built-in marketplace + repo-level marketplace |
| **OpenAI** Codex | Plugins | Küratörlü dizin (self-serve yakında) |
| **Google** Gemini CLI/Antigravity | Extensions | GitHub + built-in registry |

### Ortak Mimari
Üçü de aynı yapıyı kullanıyor:
- MCP sunucuları + custom komutlar + agent skill'leri + hook'lar
- Vendor'lar arası geçiş kolay — OpenAI bunu açıkça belirtiyor

## 🎯 Anahtar Çıkarım
AI coding agent'lar artık sadece kod yazmıyor — **ekosistem oluşturuyor**. Plugin/extension standartlaşması, MCP'nin de facto entegrasyon protokolü olduğunu teyit ediyor. Üç büyük vendor'ın aynı mimariye yakınsaması, geliştirici ekosistemi için olumlu: bir kez yaz, her yerde kullan. Codex'in "superapp" stratejisi Anthropic'in Claude Cowork hamlesiyle doğrudan rekabet ediyor.
