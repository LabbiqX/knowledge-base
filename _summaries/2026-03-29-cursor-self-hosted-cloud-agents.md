---
layout: summary
title: "Run Cloud Agents in Your Own Infrastructure"
date: 2026-03-29
source: "https://cursor.com/blog/self-hosted-cloud-agents"
category: "AI Agent Architecture"
type: "Makale"
---

## TL;DR
Cursor, self-hosted cloud agent'ları GA olarak sundu. Kod, tool execution ve build artifact'ler şirketin kendi ağında kalıyor. Worker process'ler HTTPS ile Cursor'a bağlanıyor — inbound port, firewall değişikliği, VPN gerektirmiyor. Brex, Money Forward, Notion gibi müşteriler zaten kullanıyor.

---

## Key Points
- Self-hosted: kod ve execution asla şirket ağından çıkmıyor
- Worker: HTTPS outbound bağlantı, inbound port gerektirmiyor
- Her agent session'a özel dedicated worker (long-lived veya single-use)
- Helm chart + Kubernetes operator ile büyük ölçekli dağıtım
- Non-Kubernetes için fleet management API
- Cursor inference/planning yapıyor, tool call'lar worker'da execute ediliyor
- Multi-model, plugins (skills, MCP, subagents, rules, hooks), team permissions desteği
- Yakında: video/screenshot/log demo, remote desktop takeover, automations desteği

---

## 🎯 Anahtar Çıkarım
> Self-hosted cloud agent'lar, kurumsal güvenlik gereksinimlerini karşılarken otonom coding agent yeteneklerini sunuyor — "aynı ürün, sizin altyapınız" yaklaşımıyla agent deployment'ın enterprise'a girişini hızlandırıyor.
