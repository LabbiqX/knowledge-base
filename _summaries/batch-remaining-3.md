---
layout: summary
title: "Batch Remaining 3 — Knowledge Base Özetleri"
date: 2026-03-29
source: "https://www.forbes.com/sites/bernardmarr/2026/02/23/5-vibe-coding-use-cases-every-company-can-start-using-today/"
category: "RAG & Knowledge"
type: "Makale"
---

## TL;DR
SKIP — Forbes sitesi JS gerektiriyor, 403 hatası aldı. İçerik okunamadı.

---

# OpenAI Introduces Harness Engineering: Codex Agents Power Large‑Scale Software Development

**Kaynak:** [InfoQ](https://www.infoq.com/news/2026/02/openai-harness-engineering-codex/)
**Etiketler:** `#openai` `#codex` `#software-engineering` `#ai-agents` `#harness`

## TL;DR
OpenAI, "Harness Engineering" adlı yeni bir iç mühendislik metodolojisi tanıttı. Bu metodoloji, Codex AI agent'larını kullanarak yazılım geliştirme yaşam döngüsünün büyük bölümünü otomatikleştiriyor. Beş aylık bir iç deneyde, küçük bir mühendis ekibi tek satır manuel kod yazmadan yaklaşık 1 milyon satır kod içeren bir beta ürün geliştirip yayımlayabildi.

## Ana Noktalar
- Harness, scaffold, geri bildirim döngüleri, dokümantasyon ve mimari kısıtlamaları makine tarafından okunabilir artifact'lara kodluyor
- Codex agent'ları; kod yazma, test oluşturma, CI/CD yönetimi ve observability kurulumu gibi görevleri declarative prompt'lar aracılığıyla gerçekleştiriyor
- Mühendislerin rolü: kod yazmaktan ortam tasarlamaya, niyet belirtmeye ve yapılandırılmış geri bildirim vermeye kayıyor
- Agent'lar telemetri (log, metrik, span) kullanarak uygulama performansını izliyor ve hataları izole ortamlarda yeniden üretiyor
- Mimari bağımlılıklar mekanik olarak uygulanıyor: Types → Config → Repo → Service → Runtime → UI akışı
- Martin Fowler, Harness'i "AI destekli yazılım geliştirmenin kritik parçalarından biri" olarak nitelendirdi

## Anahtar Çıkarımlar
- 🎯 1 milyon satır kod, sıfır manuel kod: AI agent'lar artık gerçek üretim ürünleri yazabiliyor
- 🎯 Yazılım mühendisliğinin geleceği "kod yazmak" değil "ortam ve niyet tasarlamak" üzerine kurulu
- 🎯 Harness, AI-driven yazılım geliştirmenin endüstri standardı olabilecek bir çerçeve sunuyor

---

# Is There a Community Edition of Palantir? Meet OpenPlanter

**Kaynak:** [MarkTechPost](https://www.marktechpost.com/2026/02/21/is-there-a-community-edition-of-palantir-meet-openplanter-an-open-source-recursive-ai-agent-for-your-micro-surveillance-use-cases/)
**Etiketler:** `#open-source` `#ai-agent` `#investigative` `#palantir` `#recursive-agent`

## TL;DR
OpenPlanter, Palantir'in açık kaynaklı alternatifi olarak konumlanan bir recursive AI investigasyon agent'ı. Hükümet verilerini, mali kayıtları ve lobicilik belgelerini analiz ederek gizli bağlantıları ve anomalileri ortaya çıkarmayı hedefliyor. "Vatandaşlar için mikro-gözetleme" sloganıyla, hükümet sizi izliyorsa siz de hükümeti izleyin diyor.

## Ana Noktalar
- **Recursive sub-agent delegation**: Ana agent maksimum 4 derinliğe kadar alt agent'lar oluşturabiliyor; büyük görevleri paralel alt görevlere bölerek context window sınırını aşıyor
- **Heterojen veri desteği**: CSV, JSON, PDF gibi farklı formatlardaki verileri eş zamanlı işleyebiliyor; entity resolution ile farklı kaynaklardaki aynı kişi/şirketi eşleştiriyor
- **Probabilistik anomali tespiti**: Varlık ilişkileri kurulduktan sonra insan gözünden kaçabilecek pattern'leri otomatik bulabiliyor
- **2026 model yığını**: OpenAI gpt-5.2, Anthropic claude-opus-4-6, Cerebras qwen-3-235b destekleniyor
- **19 uzman araç**: Dosya I/O, shell çalıştırma, web arama (Exa), planlama araçları içeriyor
- Docker ile izole konteyner ortamında çalışıyor; TUI arayüzü ve headless CLI modu mevcut

## Anahtar Çıkarımlar
- 🎯 Recursive agent mimarisi büyük investigasyon görevlerini paralel alt görevlere bölerek context limitini aşıyor
- 🎯 Açık kaynak + frontier model desteği, kurumsal düzey veri analizi kapasitesini halka açık hale getiriyor
- 🎯 Shell çalıştırma yeteneği (run_shell) agent'ın kendi analiz scriptlerini yazıp çalıştırmasını sağlıyor

---

# Alibaba Team Open-Sources CoPaw: A High-Performance Personal Agent Workstation

**Kaynak:** [MarkTechPost](https://www.marktechpost.com/2026/03/01/alibaba-team-open-sources-copaw-a-high-performance-personal-agent-workstation-for-developers-to-scale-multi-channel-ai-workflows-and-memory/)
**Etiketler:** `#alibaba` `#open-source` `#agent-framework` `#memory` `#multi-channel`

## TL;DR
Alibaba, kişisel AI agent'ları dağıtmak ve yönetmek için tasarlanmış açık kaynaklı bir çerçeve olan CoPaw'ı yayımladı. AgentScope, AgentScope Runtime ve ReMe bileşenlerini birleştiren bu workstation; kalıcı bellek, çoklu platform bağlantısı ve görev zamanlaması sunarak LLM'leri gerçek bir asistana dönüştürüyor.

## Ana Noktalar
- **Üç katmanlı mimari**: AgentScope (agent iletişim ve mantığı) + AgentScope Runtime (execution ortamı) + ReMe (bellek yönetimi)
- **Kalıcı bellek (ReMe)**: Stateless LLM API'larının aksine, agent kullanıcı tercihlerini ve geçmiş görev verilerini yerel veya bulut depolamada saklayabiliyor
- **Python tabanlı Skill Extension sistemi**: Anthropics/skills spesifikasyonunu temel alıyor; core engine değiştirilmeden yeni yetenekler eklenebiliyor (web scraping, dosya yönetimi, takvim/e-posta entegrasyonu)
- **All-Domain Access**: DingTalk, Lark (Feishu), Discord, QQ, iMessage gibi platformlarda tek instance üzerinden çalışabiliyor
- **Proaktif otomasyon**: Scheduled Tasks + Skills kombinasyonu ile reaktif sohbetten proaktif background operasyonlara geçiş (günlük araştırma sentezi, repo izleme vb.)

## Anahtar Çıkarımlar
- 🎯 "Model'den Workstation'a" paradigma kayması: Artık sadece LLM performansı değil, çalışma ortamı da kritik
- 🎯 ReMe ile kalıcı bellek statelessness sorununu çözüyor; agent zaman içinde kişiselleşiyor
- 🎯 Tek CoPaw instance'ı birden fazla mesajlaşma platformuna bağlanabiliyor — tutarlı hafıza ve bağlam korunuyor

---

# Business Leaders Agree AI Is The Future — They Just Wish It Worked Right Now

**Kaynak:** [Reuters](https://www.reuters.com/business/business-leaders-agree-ai-is-future-they-just-wish-it-worked-right-now-2025-12-16/)
**Etiketler:** `#ai-business` `#enterprise-ai` `#ai-adoption`

## TL;DR
SKIP — Reuters sitesi 401 (giriş gerektiriyor) hatası verdi. İçerik okunamadı.

---

# Claude Code vs ChatGPT Codex: Which AI Coding Agent Is Actually Better?

**Kaynak:** [Tom's Guide](https://www.tomsguide.com/ai/claude-code-vs-chatgpt-codex-which-ai-coding-agent-is-actually-better)
**Etiketler:** `#claude-code` `#codex` `#coding-agent` `#comparison` `#ai-development`

## TL;DR
Tom's Guide, Claude Code ve ChatGPT Codex (GPT-5.3 tabanlı) arasında iki kısımlı bir test gerçekleştirdi: Güvenlik açığı avı ve yaratıcı terminal oluşturma. İki araç farklı güçlere sahip; net bir kazanan yok, seçim kullanım senaryosuna bağlı.

## Ana Noktalar
- **Bug Hunt testi**: Node.js kodundaki SQL injection, setInterval hatası ve unbounded cache sorunları test edildi
  - Claude Code: "Senior Architect" modunda çalıştı; hataları öğretici analojilerle açıkladı, gereksiz kodu silmeyi önerdi
  - Codex: "Son teslim baskısındaki Lead Developer" gibi; prompt'un ötesine geçerek "Input Validation" ekledi
- **Yaratıcı Terminal testi**: Bilim kurgu romanı için komut satırı arayüzü oluşturma
  - Claude Code: ASCII art header ve CRT ekran efektleriyle görsel sci-fi estetiği yakaladı
  - Codex: "İçinde yaşanan" bir evren yarattı; Güverte 3'teki termal anomali gibi rastgele gemi olayları ekledi
- Erken 2026'da agentic coding benimsenmesi hızla artıyor (GitHub kullanımı ölçülebilir büyüme gösteriyor)

## Anahtar Çıkarımlar
- 🎯 Claude Code = Mimar: Öğretici, mimari açıdan derin, yaratıcı; öğrenmek isteyen geliştiriciler için ideal
- 🎯 Codex = Mühendis: Hızlı, savunmacı, üretime hazır; gerçek uygulama geliştirme için güçlü
- 🎯 İkisi birbirinin alternatifi değil; karmaşıklık türüne göre doğru araç seçimi yapılmalı

---

# Google Gemini's Dominance Is Over — Anthropic's New Claude Is Now the Best AI for Real Work

**Kaynak:** [Tom's Guide](https://www.tomsguide.com/ai/google-geminis-dominance-is-over-anthropics-new-claude-is-now-the-best-ai-for-real-work)
**Etiketler:** `#claude` `#gemini` `#ai-comparison` `#claude-opus` `#anthropic`

## TL;DR
Tom's Guide AI editörü, Claude Opus 4.6'nın Google Gemini 3 Flash'ı gerçek iş yüklerinde geride bıraktığını savunuyor. Hız ve multimodal özelliklerde Gemini hâlâ güçlü, ancak derin muhakeme, kodlama güvenilirliği ve uzun süreli agentic görevlerde Claude açık ara önde.

## Ana Noktalar
- **Context kullanımı**: Her iki model de 1M token destekliyor, ancak Claude'un "compaction" özelliği uzun oturumlarda bağlam tutarlılığını koruyor
- **Benchmark üstünlükleri**: Terminal-Bench 2.0'da %65.4, OSWorld'de %72.7 (Anthropic'in şimdiye kadar yayımladığı en iyi computer-use modeli)
- **Profesyonel iş değeri**: GDPval-AA benchmark'ında GPT-5.2'yi ~144 Elo puan, Opus 4.5'i ~190 puan geride bıraktı
- **Agentic yetenekler**: Claude Code'da çoklu agent işbirliği, adaptif düşünme ve geliştirici effort kontrolleri eklendi
- **Gemini'nin avantajları**: Ücretsiz, hız, video/ses multimodal, Google ekosistemi entegrasyonu, görsel üretim (Nano Banana Pro)
- **Fiyatlandırma farkı**: Gemini 3 Flash ücretsiz; Opus 4.6 için Claude Pro gerekli ($20/ay)

## Anahtar Çıkarımlar
- 🎯 2026'da "en iyi AI" kavramı hıza değil doğruluğa, sürdürülebilir muhakemeye ve agentic kapasiteye göre belirleniyor
- 🎯 Claude Opus 4.6 "konuşmak yerine yapmak" konusunda çıtayı yükseltti — gerçek iş görevlerinde öncü
- 🎯 Gemini hız ve maliyet; Claude derinlik ve güvenilirlik — seçim kullanım senaryosuna göre yapılmalı

---

## REPORT

| # | URL | Durum |
|---|-----|-------|
| 1 | Forbes - Vibe Coding | ❌ SKIP (403 - JS gerekli) |
| 2 | InfoQ - OpenAI Harness Engineering | ✅ İşlendi |
| 3 | MarkTechPost - OpenPlanter | ✅ İşlendi |
| 4 | MarkTechPost - CoPaw | ✅ İşlendi |
| 5 | Reuters - Business Leaders AI | ❌ SKIP (401 - Giriş gerekli) |
| 6 | Tom's Guide - Claude Code vs Codex | ✅ İşlendi |
| 7 | Tom's Guide - Claude vs Gemini | ✅ İşlendi |

**Toplam:** 7 link | **İşlendi:** 5 | **Skip:** 2

**Skip Listesi:**
1. `https://www.forbes.com/sites/bernardmarr/2026/02/23/5-vibe-coding-use-cases-every-company-can-start-using-today/` — 403 Forbidden (JS + ad blocker engeli)
2. `https://www.reuters.com/business/business-leaders-agree-ai-is-future-they-just-wish-it-worked-right-now-2025-12-16/` — 401 Unauthorized (abonelik duvarı)
