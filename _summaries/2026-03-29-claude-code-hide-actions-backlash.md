---
layout: summary
title: "Anthropic Claude Code'un Eylemlerini Gizlemeye Çalıştı — Geliştiriciler İsyan Etti"
date: 2026-03-29
source: "https://www.theregister.com/2026/02/16/anthropic_claude_ai_edits/"
category: "AI Coding Tools"
type: "Makale"
---

## TL;DR
Claude Code v2.1.20, dosya adlarını ve okunan satır sayısını gizleyerek output'u sadeleştirdi. Geliştiriciler isyan etti: güvenlik, context hata tespiti, token tasarrufu ve audit için dosya isimlerini görmek kritik. Boris Cherny "reduced noise" dedi ama kullanıcılar "valuable information removal" olarak değerlendirdi. Sonuçta verbose mode yeniden yapılandırıldı ama varsayılan hâlâ kısıtlı.

---

## Key Points
- v2.1.20: "Read 3 files" vs eski "filename.js (150 lines)" — dosya isimleri gizlendi
- Geliştiriciler: güvenlik, yanlış context tespiti, token israfı önleme, audit scrolling için gerekli
- Boris Cherny: "try it out for a few days" — "reduced noise" argümanı
- Topluluk: "It's not simplification, it's idiotic removal of valuable information"
- Verbose mode yeniden yapılandırıldı: file paths gösterir ama full thinking/subagent output göstermez
- "Verbose mode less verbose" paradoksu — tam detay isteyenler için kötüleşme
- "Claude cannot be trusted without constant oversight" — şeffaflık make-or-break
- Token harcama etkisi: yanlış yola girdiğini erken fark edemezsen binlerce token israf

---

## 🎯 Anahtar Çıkarım
> AI araçlarında şeffaflık vs basitlik dengesi kritik — geliştiriciler "less noise" değil "right noise" istiyor ve AI'ın ne yaptığını göremezlerse güven kaybı kaçınılmaz.
