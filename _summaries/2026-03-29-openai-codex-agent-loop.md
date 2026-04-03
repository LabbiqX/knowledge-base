---
layout: summary
title: "Unrolling the Codex Agent Loop"
date: 2026-03-29
source: "https://openai.com/index/unrolling-the-codex-agent-loop/"
category: "AI Coding Tools"
type: "Makale"
---

## TL;DR
OpenAI, Codex CLI'ın çekirdek agent loop'unu detaylı açıklıyor. Döngü: kullanıcı input → prompt oluştur → model inference → tool call veya final response. Tool call çıktısı prompt'a eklenir, döngü model tool call isteyi durdurana kadar devam eder. Context window yönetimi agent'ın sorumluluğu. Prompt yapısı: system → developer instructions → tools → user instructions (AGENTS.md + skills) → user message. Responses API üzerinden çalışır.

---

## Agent Loop Yapısı
1. Kullanıcı input'u al
2. Prompt oluştur (instructions + tools + input)
3. Model inference → output tokens
4. İki sonuç: (a) assistant message (son yanıt) veya (b) tool call
5. Tool call ise: çalıştır, çıktıyı prompt'a ekle, 3'e dön
6. Döngü assistant message gelene kadar devam

## Prompt Katmanları (Öncelik sırasıyla)
| Role | İçerik | Kaynak |
|------|--------|--------|
| **System** | API server tarafından oluşturulur | Responses API |
| **Developer** | Sandbox kuralları + config.toml developer_instructions | Codex CLI |
| **User** | AGENTS.override.md → AGENTS.md → Skills metadata | Proje dizini |
| **User** | Kullanıcının mesajı | Kullanıcı |

## Teknik Detaylar
- Codex harness: CLI, Cloud, VS Code extension → ortak agent loop
- Responses API endpoint'leri: ChatGPT backend, API key, lokal (ollama/LM Studio)
- MCP server tool'ları sandbox dışı — kendi guardrail'lerini uygulamalı
- User instructions toplama: AGENTS.override.md → AGENTS.md → proje dizininden yukarı doğru tarama
- Skills: metadata + kullanım talimatı eklenir
- Context window: konuşma uzadıkça prompt büyür, yönetim agent'ın işi

## Codex vs Claude Code Karşılaştırma
- Codex: AGENTS.md, Claude Code: CLAUDE.md — benzer konsept
- Codex: Responses API, Claude Code: Messages API
- İkisi de: tools, MCP, skills, sandbox mekanizması
- Codex açık kaynak (github.com/openai/codex)

---

## 🎯 Anahtar Çıkarım
> Agent loop deceptively basit: input → inference → tool call → döngü. Ama gerçek karmaşıklık prompt assembly'de — system/developer/user katmanları, tool tanımları, skills lazy-loading, context window yönetimi. Sandbox sadece Codex'in kendi shell tool'una uygulanır, MCP tool'ları kendi güvenliğinden sorumlu — bu güvenlik açısından kritik bir fark.
