---
layout: summary
title: "Google A2UI: Open Source Protocol for Agent-Driven Interfaces"
date: 2026-03-29
source: "https://www.marktechpost.com/2025/12/22/google-introduces-a2ui-agent-to-user-interface-an-open-sourc-protocol-for-agent-driven-interfaces/"
category: "Google & Gemini"
type: "Makale"
---

## TL;DR
Google open-sourced A2UI (Agent-to-User Interface), a protocol that lets AI agents describe rich native interfaces via declarative JSON instead of outputting HTML/JavaScript. Agents reference a client-controlled catalog of trusted components (Card, Button, TextField etc.), and the client renders them using native widgets (Angular, Flutter, React, SwiftUI). Designed for security (data-only, no executable code), LLM-friendliness (flat list, streaming), and cross-framework portability.

---

## Key Points
- Agents output JSON UI descriptions, not executable code — security by design
- Client maintains catalog of trusted components; agent can only reference these
- Framework agnostic: same payload renders on Angular, Flutter, React, SwiftUI
- LLM-friendly flat representation supports streaming and incremental updates
- Solves multi-agent mesh problem: remote agents can send UI across trust boundaries
- Transport agnostic: works with A2A protocol and AG UI
- Progressive rendering: partial interfaces shown while agent computes
- v0.8 public preview, Apache 2.0 license
- Already used in Opal, Gemini Enterprise, Flutter GenUI

---

## 🎯 Anahtar Çıkarım
> A2UI, agent'ların "sadece metin" yerine "zengin UI" üretmesini güvenli ve framework-agnostik şekilde mümkün kılıyor — multi-agent sistemlerde UI injection riskini ortadan kaldıran deklaratif yaklaşım.
