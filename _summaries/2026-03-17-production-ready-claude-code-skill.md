---
layout: summary
title: "How to Build a Production-Ready Claude Code Skill"
date: 2026-03-17
source: "https://towardsdatascience.com/how-to-build-a-production-ready-claude-code-skill/"
category: "AI Coding Tools"
type: "Makale"
---

## TL;DR
Claude Code Skill'leri tekrarlayan iş akışlarını paketleyen "akıllı prompt"lar. Progressive disclosure sayesinde context window şişmez. En kritik nokta: **description spesifik ve "pushy" olmalı** — Claude varsayılan olarak skill tetiklemeyi atlar. 3 pattern var: Prompt-Only (en basit), Prompt+Scripts (veri işleme), Skill+MCP/Subagent (dış API'ler). Gerçekçi/dağınık promptlarla test et, temiz promptlar gerçeği yansıtmaz. Şüpheliysen Pattern A ile başla.

---

## Konu
Claude Code Skill'lerini sıfırdan tasarlama, geliştirme ve dağıtma rehberi.

## Skill Nedir?
- Claude'a belirli görevleri öğreten yapılandırılmış talimat setleri
- **Progressive disclosure** ile çalışır: Metadata (~100 token) → SKILL.md → scripts/references
- Çok sayıda skill yüklenebilir, context window şişmez
- Tekrarlayan uzun prompt'ları Skill'e dönüştür

## Skill vs MCP vs Subagent
- **Skill** = Tarif (nasıl davranılacağı)
- **MCP** = Mutfak (araçlar, API bağlantıları)
- **Subagent** = Bağımsız çalışan ayrı bir context
- Birlikte kullanılabilirler: PR analiz iş akışı Skill'de, hata verisi MCP ile çekilir

## Tasarım İlkeleri
- 2-3 somut kullanım senaryosu ile başla, kullanıcının gerçekte ne yazacağını hayal et
- Description **spesifik ve "pushy"** olmalı — Claude varsayılan olarak Skill tetiklemeyi atlar
- Name: max 64 karakter | Description: max 1024 karakter
- Tetikleme anahtar kelimelerini açıkça listele

## Üç Uygulama Paterni
1. **Pattern A (Prompt-Only):** Sadece Markdown — stil rehberleri, coding standards, commit formatı
2. **Pattern B (Prompt + Scripts):** Markdown + Python/JS — veri işleme, doğrulama, rapor üretimi
3. **Pattern C (Skill + MCP/Subagent):** Dış API'ler gerektiren karmaşık iş akışları

> 💡 **Karar ağacı:** Dış API lazım mı? → C | Deterministik işlem var mı? → B | Claude'un yargısı yeterli mi? → A. Şüpheliysen A ile başla.

## Test & Dağıtım
- Gerçekçi, "dağınık" promptlarla test et — temiz promptlar gerçeği yansıtmaz
- İterasyon döngüsü: çalıştır → değerlendir → düzelt → tekrarla
- Dağıtım: ZIP upload (claude.ai) veya `.claude/skills/` dizini (repo paylaşımı)
- Versiyon numarasını güncelle, API key hardcode etme

---

## 🎯 Anahtar Çıkarım
> Skill'in tetiklenip tetiklenmemesi tamamen description'a bağlı. Claude varsayılan olarak Skill kullanmayı atlar — description spesifik, pushy ve tetikleme koşullarını açıkça listeleyen şekilde yazılmalı.
