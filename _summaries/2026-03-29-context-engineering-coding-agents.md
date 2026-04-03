---
layout: summary
title: "Context Engineering for Coding Agents"
date: 2026-03-29
source: "https://martinfowler.com/articles/exploring-gen-ai/context-engineering-coding-agents.html"
category: "AI Coding Tools"
type: "Makale"
---

## TL;DR
Context engineering = modelin gördüğünü düzenleyerek daha iyi sonuç almak. Coding agent'lar için prompt'un ötesinde yapılandırılmış bir context sistemi gerekli: CLAUDE.md (her zaman yüklü rehber), Rules (dosya bazlı koşullu), Skills (lazy-load, LLM karar verir), Subagents (kendi context window'unda paralel iş), Hooks (deterministik lifecycle event'lar), MCP (harici araç erişimi). Uyarı: "kontrol illüzyonu" — context engineering olasılıkları artırır ama garanti vermez.

---

## Context Kategorileri
- **Instructions:** Agent'a ne yapacağını söyle ("E2E testi şu şekilde yaz")
- **Guidance (Rules/Guardrails):** Genel konvansiyonlar ("Testler birbirinden bağımsız olsun")

## Context Interfaces
- **Tools:** Dahili yetenekler (bash, dosya arama)
- **MCP Servers:** Harici API/veri erişimi (JIRA, browser, knowledge base)
- **Skills:** LLM'in gerekli gördüğünde lazy-load ettiği ek kaynaklar

## Kim Yükler?
| Yükleyici | Avantaj | Dezavantaj |
|-----------|---------|------------|
| **LLM** | Otonom çalışma, ölçeklenebilir | Non-deterministik — beklediğinde yüklemeyebilir |
| **İnsan** | Kontrollü | Otomasyonu azaltır |
| **Agent yazılımı** | Deterministik, öngörülebilir | Esneklik az |

## Claude Code Context Sistemi
| Özellik | Ne | Kim Yükler |
|---------|-----|-----------|
| **CLAUDE.md** | Genel rehber, her oturumda yüklü | Claude Code (otomatik) |
| **Rules** | Dosya bazlı rehber (*.sh, *.ts) | Claude Code (dosya yüklenince) |
| **Skills** | Lazy-load: rehber, talimat, script | LLM veya insan |
| **Subagents** | Kendi context window'u, paralel | LLM veya insan |
| **MCP Servers** | Harici araç erişimi | LLM |
| **Hooks** | Lifecycle event'larında deterministik script | Claude Code |
| **Plugins** | Tüm bunları dağıtma mekanizması | — |

## Paylaşım Zorlukları
- Bağlam benzerliği şart — takım içi paylaşım > internet'ten kopyalama
- Overengineering riski — iteratif olarak oluştur
- Farklı deneyim seviyeleri farklı kurallar gerektirir
- Yabancıdan kopyalanan context'te farkında olmadan çelişkili talimat verme riski

## Kontrol İllüzyonu ⚠️
- "X'i garanti et" veya "hallucination'ı önle" = yanlış beklenti
- Context engineering olasılıkları artırır ama kesinlik sağlamaz
- LLM varsa olasılıklarla düşünmeli, uygun insan denetimiyle birleştirmeli

---

## 🎯 Anahtar Çıkarım
> Context engineering "mühendislik" gibi görünse de aslında olasılıksal — LLM tüm talimatları alır ama yorumlama hala modele bağlı. En iyi yaklaşım: iteratif oluştur, minimum gerekli context'i yükle, Skills ile lazy-load kullan. "Kontrol illüzyonu"na düşme — insan denetimini doğru seviyede tut.
