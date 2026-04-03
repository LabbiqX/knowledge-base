---
layout: summary
title: "The Case for Running AI Agents on Markdown Files Instead of MCP Servers"
date: 2026-03-29
source: "https://thenewstack.io/skills-vs-mcp-agent-architecture/"
category: "AI Agent Architecture"
type: "Makale"
---

## TL;DR
Developers are replacing bloated MCP servers with Markdown skill files, cutting token costs by up to 100x. A two-layer architecture is emerging: SKILL.md files for knowledge (stable workflows, guardrails, decision logic) and MCP servers for actions (dynamic API calls). Brad Feld's CompanyOS runs an entire company on 12 Markdown files. The GitHub MCP server uses ~50K tokens; a SKILL.md file achieves the same in ~200 tokens.

---

## Key Points
- Two categories of agent tasks: knowing something (knowledge) vs. doing something (action)
- Knowledge problems → SKILL.md files (stable, natural language, fits in context window)
- Action problems → MCP servers (dynamic API access, real-time data)
- CompanyOS: entire company run on 12 Markdown files + 8 MCP servers; intelligence lives in Markdown
- Sentry's David Cramer: "many MCP servers don't need to exist"
- GitHub MCP server: ~50K tokens → SKILL.md equivalent: ~200 tokens (100x reduction)
- Supabase, Microsoft .NET Skills Executor already adopting this pattern

---

## 🎯 Anahtar Çıkarım
> The winning agent architecture separates knowledge (Markdown skill files) from capability (MCP servers). Most MCP servers solve knowledge problems that don't need runtime infrastructure — a SKILL.md file does the same job at 100x fewer tokens.
