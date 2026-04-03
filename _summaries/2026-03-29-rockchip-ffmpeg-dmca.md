---
layout: summary
title: "GitHub Takes Down Rockchip MPP Repository After FFmpeg Copyright Claim"
date: 2026-03-29
source: "https://linuxiac.com/github-takes-down-rockchip-mpp-repository-after-ffmpeg-copyright-claim/"
category: "AI Agent Architecture"
type: "GitHub"
---

## TL;DR
GitHub disabled Rockchip's Media Process Platform (MPP) repository after a DMCA takedown by an FFmpeg contributor. Rockchip allegedly copied FFmpeg's LGPL-licensed codec implementations (AV1, H.265, VP9), relicensed them under Apache License (incompatible with LGPL), and removed original copyright headers. Rockchip was warned 2 years ago but took no corrective action.

---

## Key Points
- LGPL permits reuse but requires maintaining LGPL-compatible license and attribution
- Rockchip relicensed under Apache License — incompatible with LGPL
- Removed original copyright headers and author information
- Evidence: identical structures, comments, and FFmpeg function name references
- Rockchip was notified ~2 years ago, repeatedly promised but never fixed
- Repository remains unavailable, no counter-notice filed
- Rockchip SoCs widely used in SBCs, Android devices, media players

---

## 🎯 Anahtar Çıkarım
> Açık kaynak lisans uyumluluğu ciddi bir sorun. LGPL kodunu Apache'ye çevirip atıf kaldırmak, yıllar sonra bile DMCA takedown'a yol açabiliyor. Embedded Linux ekosistemi bu repo kaybından etkilenecek.
