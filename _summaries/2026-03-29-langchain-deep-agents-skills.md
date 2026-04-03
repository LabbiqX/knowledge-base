---
layout: summary
title: "Deep Agents Skills: Extending Agent Capabilities"
date: 2026-03-29
source: "https://docs.langchain.com/oss/python/deepagents/skills"
category: "AI Agent Architecture"
type: "Makale"
---

## TL;DR
LangChain Deep Agents, Agent Skills spesifikasyonunu takip eden bir skill sistemi sunuyor. Her skill bir klasör: SKILL.md (talimatlar + metadata), opsiyonel scriptler, referans dosyaları ve template'ler. Agent başlangıçta sadece frontmatter'ı okur, eşleşen prompt geldiğinde tüm skill dosyalarını inceler — bu "progressive disclosure" yaklaşımı token tasarrufu sağlıyor.

---

## Key Points
- Skill = klasör: SKILL.md + scriptler + referans dosyaları + asset'ler
- SKILL.md frontmatter: name, description, license, compatibility, metadata, allowed-tools
- **Progressive disclosure:** Agent başlangıçta sadece description'ları tarar, eşleşme olunca detaya iner
- 3 backend desteği: StateBackend, StoreBackend (Postgres), FilesystemBackend
- Description 1024 karakterle sınırlı; SKILL.md 10 MB altında olmalı
- Agent Skills specification (agentskills.io) standardını takip ediyor
- LangChain Skills repo'da hazır skill'ler mevcut

---

## 🎯 Anahtar Çıkarım
> Agent skill'leri, "her şeyi system prompt'a yaz" yerine modüler, progressive disclosure yaklaşımıyla agent yeteneklerini genişletiyor — standardize edilmiş format sayesinde skill'ler framework'ler arası taşınabilir.
