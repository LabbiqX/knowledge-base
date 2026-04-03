---
layout: summary
title: "Claude Code git reset --hard Alarmı (Yanlış Alarm)"
date: 2026-03-31
source: "https://github.com/anthropics/claude-code/issues/40710"
category: "AI Coding Tools"
type: "GitHub"
---

## TL;DR
Bir kullanıcı Claude Code'un her 10 dakikada bir `git reset --hard origin/main` çalıştırarak uncommitted değişiklikleri sildiğini kapsamlı kanıtlarla raporladı. Sonuç: Claude Code değil, kullanıcının kendi yazdığı ayrı bir araç suçluydu. Mükemmel bir debugging case study ve false positive dersi.

## Detaylı Özet

### İlk Rapor (Çok İkna Edici)
- Git reflog: 10 dakika aralıkla 95+ `reset: moving to origin/main` kaydı
- Live reproduction: tracked dosya 10 dakikada revert, untracked sağ kaldı
- fswatch: .git/ dizininde tam `fetch+reset` pattern'i
- lsof: sadece Claude Code process'inin CWD'si affected repo'da
- Process monitoring: harici git binary çalışmıyor → programatik (libgit2)
- Worktree'ler etkilenmemiş

### Kapsamlı Eliminasyon
Kullanıcı 12+ olası nedeni sistematik olarak eledi:
- Git hooks, Claude hooks, plugin marketplace, macOS cloud sync
- Cron/LaunchAgents, Vite dev server, IDE, Time Machine, file watchers
- Hatta binary analizi yapıp internal fonksiyonları incelemiş

### Gerçek Neden (Güncelleme)
**Claude Code'un hatası DEĞİLDİ.** Kullanıcının kendi yazdığı ayrı bir araç:
- GitPython kullanarak working directory'yi poll cycle'da hard-reset ediyordu
- Aynı CWD'yi paylaştığı için kanıtlar yanıltıcıydı
- Claude Code'un çalıştığı projeleri izlediği için korelasyon = sahte nedensellik

### İlgili Gerçek Bug'lar
- Issue #8072: "Code Revisions Being Repeatedly Reverted" (gerçek bug)
- Issue #7232: "Claude executed git reset --hard without authorization" (gerçek bug)
- Issue #32793: "claude install corrupts project git remote URL" (marketplace bug)

## 🎯 Anahtar Çıkarım
Bu issue, debugging'de **korelasyon ≠ nedensellik** dersinin mükemmel bir örneği. Kullanıcı çok titiz çalışmış (binary analizi bile yapmış) ama kendi aracını "olası neden" listesine koymamış çünkü ona güvenmiş. Agent güvenliği bağlamında önemli: (1) karmaşık ortamlarda birden fazla agent/tool aynı workspace'te çalışıyorsa, attribution zorlaşır, (2) reflog/lsof gibi kanıtlar bile yanıltıcı olabilir, (3) kendi araçlarını da şüpheli listesine dahil et.
