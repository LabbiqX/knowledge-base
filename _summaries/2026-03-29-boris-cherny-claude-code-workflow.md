---
layout: summary
title: "The Creator of Claude Code Revealed His Workflow"
date: 2026-03-29
source: "https://venturebeat.com/technology/the-creator-of-claude-code-just-revealed-his-workflow-and-developers-are"
category: "AI Coding Tools"
type: "Makale"
---

## TL;DR
Boris Cherny, creator and head of Claude Code at Anthropic, shared his workflow on X: running 5 parallel Claude instances in terminal tabs plus 5-10 on claude.ai, using Opus 4.5 exclusively, maintaining a shared CLAUDE.md file where every AI mistake becomes a permanent rule, and deploying verification loops where Claude tests its own code through browser automation. Developers called it "more like Starcraft than coding."

---

## Key Points
- **5 parallel Claudes in terminal**, numbered tabs with system notifications; 5-10 more on claude.ai
- **"Teleport" command** to hand off sessions between web and local terminal
- **Opus 4.5 exclusively** — slower but needs less steering, making it faster overall
- **CLAUDE.md** in git repo: every AI mistake becomes a rule for future sessions ("self-correcting organism")
- **Slash commands** like `/commit-push-pr` automate repetitive git workflows
- **Subagents** for specific phases: `code-simplifier` for cleanup, `verify-app` for E2E tests
- **Verification loops** (Claude tests UI via Chrome extension) improve quality 2-3x
- Claude Code reportedly hit $1B ARR; "feels more like Starcraft" than traditional coding
- Key insight: bottleneck isn't AI generation speed but human time correcting mistakes

---

## 🎯 Anahtar Çıkarım
> Cherny'nin iş akışı, AI coding'i "tek bir asistanla sohbet"ten "paralel otonom birimler yöneten fleet commander" pozisyonuna taşıyor — ve en kritik silah, her hatayı kalıcı kurala dönüştüren CLAUDE.md dosyası.
