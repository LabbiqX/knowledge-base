---
layout: summary
title: "Building a C Compiler with a Team of Parallel Claudes"
date: 2026-03-29
source: "https://www.anthropic.com/engineering/building-c-compiler"
category: "Anthropic & Claude"
type: "Makale"
---

## TL;DR
Nicholas Carlini 16 paralel Claude agent'ı ile sıfırdan Rust tabanlı bir C derleyicisi yazdırdı — Linux kernel 6.9'u x86, ARM ve RISC-V'de derleyebiliyor. ~2000 Claude Code session'ı, $20K API maliyeti, 100K satır kod. Agent'lar basit bir while-true döngüsünde çalışıyor, git üzerinden senkronize, lock dosyalarıyla görev paylaşımı. İnsan müdahalesi minimal — asıl iş test harness ve ortam tasarımında.

---

## Harness Tasarımı
- **Basit döngü:** `while true; do claude --dangerously-skip-permissions -p "$(cat AGENT_PROMPT.md)"; done`
- Container'da çalışır — gerçek makinede değil
- Agent prompt: sorunu küçük parçalara böl, takip et, sonraki işi belirle, mükemmel olana kadar devam et
- Bir agent yanlışlıkla `pkill -9 bash` çalıştırıp kendini öldürdü 😄

## Paralel Çalışma
- Her agent → Docker container → bare git repo'dan clone → push
- **Senkronizasyon:** `current_tasks/` dizinine lock dosyası yaz, git çakışma zorla farklı iş seçtir
- Merge conflict'ler sık ama Claude çözebiliyor
- Orkestrasyon agent'ı yok — her agent "sonraki en bariz problemi" seçer

## Önemli Dersler

### Yüksek Kaliteli Testler
- Task verifier neredeyse mükemmel olmalı — yoksa Claude yanlış problemi çözer
- CI pipeline eklendi: yeni commit'ler mevcut kodu bozamaz
- Test suite: derleyici test paketleri + açık kaynak proje derleme (SQLite, Redis, Lua)

### Claude'un Gözünden Bak
- **Context window kirliliği:** Test binlerce satır basmamalı, log dosyasına yaz, `ERROR` ile grep'lenebilir format
- **Zaman körlüğü:** Claude saatlerce test çalıştırabilir — `--fast` ile %1-10 sample, agent başına deterministik ama VM'ler arası random
- README ve progress dosyalarını sık güncele — her yeni agent sıfırdan başlıyor

### Paralelliği Kolaylaştır
- Bağımsız testler varken kolay: her agent farklı test
- Linux kernel = tek büyük görev → tüm agent'lar aynı bug'ı buluyordu
- **Çözüm:** GCC'yi oracle olarak kullan, random dosyaları GCC ile derle, sorunlu dosyaları izole et
- Delta debugging: birlikte fail eden ama tek başına çalışan dosya çiftlerini bul

### Agent Rolleri
- Duplikasyon temizleyici, performans optimizasyoncu, verimli kod üretici
- Rust developer perspektifinden yapısal kritik
- Uzmanlaşma parallelism'in doğal uzantısı

---

## 🎯 Anahtar Çıkarım
> İnsan müdahalesi sıfıra yakın ama insan tasarımı kritik — asıl iş test harness, ortam ve feedback loop tasarımında. Agent'ları yönetmek değil, agent'ların kendilerini yönetebileceği ortamı tasarlamak esas beceri. "Context window kirliliği" ve "zaman körlüğü" gibi LLM sınırlamalarını tasarımla çözmek gerekiyor.
