---
layout: summary
title: "AI-Resistant Technical Evaluations: How Anthropic Keeps Its Hiring Tests Ahead of Claude"
date: 2026-03-29
source: "https://www.anthropic.com/engineering/AI-resistant-technical-evaluations"
category: "Agent Evaluation"
type: "Makale"
---

## TL;DR
Anthropic's performance engineering take-home test has been completed by 1,000+ candidates, but each new Claude model defeats it. Claude Opus 4 outperformed most humans; Opus 4.5 matched even top candidates. The team has iterated through 3 versions, learning that AI-resistant evaluations require problems with depth that exceed model capabilities within time constraints, while humans with unlimited time can still outperform models.

---

## Key Points
- Original test: optimize code for a simulated accelerator (like TPUs) — parallel tree traversal problem
- Claude 3.7 Sonnet: 50%+ candidates would've been better off delegating entirely to Claude Code
- Claude Opus 4: outperformed almost all humans within 4-hour time limit
- Claude Opus 4.5: matched even top candidates' performance
- Fix strategy: use Claude to identify where it struggles, make that the new starting point
- Design principles: representative of real work, high signal, no domain-specific knowledge required, fun
- Shortened from 4 hours to 2 hours over iterations
- Candidates explicitly allowed to use AI tools (as they would on the job)
- Open challenge released: if you can beat Opus 4.5, Anthropic wants to hear from you

---

## 🎯 Anahtar Çıkarım
> As AI models improve, technical evaluations must evolve faster — the only surviving strategy is depth that exceeds what models can achieve under time constraints, turning hiring into a continuous arms race with your own AI.
