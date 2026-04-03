---
layout: summary
title: "Open SWE: An Open-Source Framework for Internal Coding Agents"
date: 2026-03-29
source: "https://blog.langchain.com/open-swe-an-open-source-framework-for-internal-coding-agents/"
category: "AI Coding Tools"
type: "Makale"
---

## TL;DR
LangChain, Stripe (Minions), Ramp (Inspect), Coinbase (Cloudbot) gibi şirketlerin bağımsız olarak geliştirdiği iç coding agent mimarilerindeki ortak kalıpları açık kaynak bir framework'te topladı. Open SWE, Deep Agents üzerine inşa edilmiş, izole sandbox'lar, küratörlü toolset, subagent orkestrasyon, Slack/Linear/GitHub entegrasyonu sunan bir framework.

---

## Key Points
- **Ortak kalıplar:** İzole sandbox'lar, küratörlü toolset'ler, Slack-first invokasyon, zengin başlangıç context'i, subagent orkestrasyon
- **Mimari:** Deep Agents + LangGraph üzerine inşa — fork yerine composition yaklaşımı
- **Sandbox:** Modal, Daytona, Runloop, LangSmith destekli izole ortamlar
- **Toolset:** execute, fetch_url, http_request, commit_and_open_pr, linear_comment, slack_thread_reply + Deep Agents yerleşik araçları
- **Context:** AGENTS.md + kaynak context (Linear/Slack) iki katmanlı yaklaşım
- **Middleware:** check_message_queue (takip mesajları), open_pr_if_needed (güvenlik ağı), ToolErrorMiddleware
- **Invokasyon:** Slack mention, Linear @openswe comment, GitHub PR comment

---

## 🎯 Anahtar Çıkarım
> İç coding agent'ları bağımsız geliştiren şirketler aynı mimari kalıplara yakınsadı — Open SWE bu kalıpları açık kaynak, özelleştirilebilir bir framework'te topluyor ve "fork etme, compose et" yaklaşımı benimsiyor.
