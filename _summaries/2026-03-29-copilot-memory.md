---
layout: summary
title: "About Agentic Memory for GitHub Copilot"
date: 2026-03-29
source: "https://docs.github.com/en/copilot/concepts/agents/copilot-memory"
category: "AI Coding Tools"
type: "GitHub"
---

## TL;DR
GitHub Copilot now has persistent, repository-scoped "memories" that allow it to learn from a codebase over time. Memories are tightly scoped facts deduced during work, validated against current code before use, and automatically deleted after 28 days to prevent staleness. This reduces repeated prompt engineering and manual instruction file maintenance.

---

## Key Points
- Memories are repository-specific and created from Copilot activity by users with write permission
- Cross-feature sharing: coding agent discoveries can inform code review, and vice versa
- Memories validated against current codebase citations before use
- Auto-deleted after 28 days; validated+used memories get refreshed
- Works with Copilot coding agent, code review, and CLI
- Enabled by default for Pro/Pro+ individual plans; off by default for enterprise
- Repository owners can review and manually delete memories

---

## 🎯 Anahtar Çıkarım
> Copilot Memory, AI asistanların kod tabanını zamanla "öğrenmesini" sağlayan ilk büyük ölçekli kalıcı hafıza uygulaması. Bu yaklaşım, custom instructions dosyalarını gereksiz kılma potansiyeline sahip.
