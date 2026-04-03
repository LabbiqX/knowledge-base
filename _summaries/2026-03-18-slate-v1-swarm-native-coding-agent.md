---
layout: summary
title: "Slate V1: İlk \"Swarm-Native\" Otonom Kodlama Agent'ı"
date: 2026-03-18
source: "https://venturebeat.com/orchestration/y-combinator-backed-random-labs-launches-slate-v1-claiming-the-first-swarm"
category: "Multi-Agent Systems"
type: "Makale"
---

## TL;DR
Y Combinator destekli Random Labs, **Slate V1**'i çıkardı — "swarm-native" bir kodlama agent'ı. Tek model yerine **birden fazla LLM'i paralel orkestre ediyor**: Claude Sonnet strateji, GPT-5.4 kod çalıştırma, GLM 5 araştırma yapıyor. "Thread Weaving" mimarisi ile context window'u RAM gibi yönetiyor, lossy compaction yerine **episodik hafıza** kullanıyor. Terminal Bench 2.0'da standart agent'ların %20 başarı gösterdiği görevde %66 başardı.

---

## Problem
AI modelleri güçleniyor ama gerçek darboğaz "systems problem" — uzun vadeli ve derin bağlam gerektiren görevlerde model zekası düşüyor. Tek model, strateji ve taktik arasında boğuluyor (**Knowledge Overhang**: model bilgiyi biliyor ama taktik yükten dolayı erişemiyor).

## Çözüm: Thread Weaving Mimarisi

**OS benzeri yaklaşım** (Karpathy'nin "LLM OS" konseptinden ilham):

- **Kernel (Orchestrator):** Merkezi orkestrasyon thread'i — strateji yönetir, kod yazmaz
- **Worker Processes:** Paralel worker thread'ler — spesifik, sınırlandırılmış görevler yürütür
- TypeScript DSL ile paralel görev dağıtımı
- Context window = RAM gibi yönetilir — ne tutulacağı, ne atılacağı aktif olarak kontrol edilir

## Episodik Hafıza (Compaction Yerine)
- Çoğu agent "compaction" kullanır → lossy sıkıştırma, kritik bilgi kaybolabilir
- Slate **episode** üretir: worker tamamlandığında uzun transcript yerine başarılı adımların özeti döner
- Episode'lar orchestrator ile doğrudan bağlam paylaşır → "swarm zekası" korunur

## Multi-Model Orkestrasyon
Her göreve en uygun modeli atama:
- **Claude Sonnet** → karmaşık refactoring stratejisi
- **GPT-5.4** → kod çalıştırma
- **GLM 5** → kütüphane dokümantasyonu araştırma
- Basit taktik adımlarda pahalı model kullanmama → maliyet optimizasyonu

## Sonuçlar
- Terminal Bench 2.0, make-mips-interpreter görevi: Standart agent'lar (Opus 4.6 dahil) **<%20** → Slate **%66 başarı**
- Değişen/mutasyonlu ortamlarda stabilite

## İş Modeli
- Usage-based credit model (CLI'dan `/usage`, `/billing` ile takip)
- Organizasyon seviyesinde billing — profesyonel takımlara yönelik
- OpenAI Codex ve Claude Code entegrasyonu yakında
- Rakip değil, **orkestrasyon katmanı** olarak konumlanıyor

---

## 🎯 Anahtar Çıkarım
> Geleceğin yazılım mühendisi tek bir modelle çalışmayacak — **uzmanlaşmış modellerin swarm'ını yönetecek.** Slate'in Thread Weaving mimarisi, context window'u RAM gibi yöneterek ve episodik hafıza ile lossy compaction sorununu çözerek, standart agent'ların %20'de kaldığı görevlerde %66 başarı sağlıyor.
