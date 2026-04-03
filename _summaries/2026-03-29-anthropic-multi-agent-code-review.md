---
layout: summary
title: "Anthropic Launches a Multi-Agent Code Review Tool for Claude Code"
date: 2026-03-29
source: "https://thenewstack.io/anthropic-launches-a-multi-agent-code-review-tool-for-claude-code/"
category: "Multi-Agent Systems"
type: "Makale"
---

## TL;DR
Anthropic launched Code Review in Claude Code, a multi-agent system that dispatches parallel review agents to catch bugs before human reviewers see the code. Available for Claude Teams and Enterprise users, it runs automatically when PRs are opened on enabled repositories. It's more thorough (and expensive) than the existing GitHub Actions code review.

---

## Key Points
- AI coding tools are causing a surge in PRs, shifting the bottleneck to code review
- Code Review dispatches a team of agents working in parallel, each checking different error types
- Available for Claude Teams and Enterprise in Claude Code web interface
- Can be enabled per-repository by admins
- More thorough than the existing open-source GitHub Action code review
- Addresses the asymmetry: one prompt generates a PR, but reviewers spend significant time verifying edge cases

---

## 🎯 Anahtar Çıkarım
> As AI coding tools multiply the volume of PRs, Anthropic's multi-agent Code Review addresses the new bottleneck by parallelizing review across specialized agents — each hunting different types of bugs simultaneously.
