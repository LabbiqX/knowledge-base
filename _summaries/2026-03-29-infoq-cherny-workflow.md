---
layout: summary
title: "Inside the Development Workflow of Claude Code's Creator (InfoQ)"
date: 2026-03-29
source: "https://www.infoq.com/news/2026/01/claude-code-creator-workflow/"
category: "AI Coding Tools"
type: "Makale"
---

## TL;DR
InfoQ's detailed breakdown of Boris Cherny's Claude Code workflow at Anthropic: 5 local parallel sessions (each with own git checkout, not branches), 5-10 remote sessions, Opus 4.5 exclusively, plan-first then auto-accept edits, CLAUDE.md (2.5k tokens) for cumulative learning, PostToolUse hooks for auto-formatting, slash commands for daily workflows, and verification via Chrome extension testing every change.

---

## Key Points
- Each local session uses its own git checkout (not branches/worktrees) to avoid conflicts
- 10-20% of remote sessions abandoned due to unexpected scenarios
- Plan mode first → refine iteratively → switch to auto-accept edits for 1-shot execution
- CLAUDE.md maintained per team in git: mistakes, style conventions, design guidelines, PR templates
- Uses `@.claude` tag on PR reviews to add learnings to CLAUDE.md
- PostToolUse hook runs `bun run format` after every Write/Edit to prevent CI failures
- Never uses `--dangerously-skip-permissions` except for sandboxed long-running tasks
- `/permissions` to whitelist safe bash commands (bun run build/test)
- Verification via Chrome extension: "tests the UI, iterates until code works and UX feels good"
- Result: team focuses on code review and steering; PR code is already in good shape

---

## 🎯 Anahtar Çıkarım
> Cherny'nin iş akışının özü: "plan → execute → verify" döngüsü, her hatayı kalıcı bilgiye dönüştüren CLAUDE.md ve otomatik formatting hook'ları — disiplin, raw AI gücünden daha önemli.
