---
layout: summary
title: "Knowledge Base — Batch Remaining 2"
date: 2026-03-29
source: "https://thenewstack.io/in-2026-ai-is-merging-with-platform-engineering-are-you-ready/"
category: "RAG & Knowledge"
type: "Makale"
---

## TL;DR
2025'te AI'nın yazılım geliştirme ekiplerini güçlendirdiği (yerini almadığı) anlaşıldı. 2026'da platform mühendisliği ile AI birleşiyor; AI'ı güvenli ve verimli deploy etmek için internal platform stratejisi altın standart haline geliyor.

## Ana Noktalar
- Platform mühendisliği, AI araçlarını güvenli şekilde deploy etmek için golden path'ler oluşturuyor
- Çoğu kuruluş CNCF Platform Engineering Maturity Model'in "operational" (2. kademe) seviyesinde
- AI coding assistant'lar ile PagerDuty gibi şirketler büyük kod tabanlarında kitlesel değişiklikler yapabiliyor
- Ölçüm metrikleri: DORA, SPACE, DX Core 4 kombinasyonu yaygın
- Sadece platform stratejisiyle AI'ı benimseyenler rekabette öne geçecek
- Developer Experience (DevEx), platform ve AI entegrasyonunun odak noktası olmaya devam ediyor
- Küçük takımlar (< 12 geliştirici) hâlâ ad hoc yapıda ilerleyebilir

## Anahtar Çıkarımlar
- 🎯 AI + Platform Engineering = 2026'nın dominant trendi; gateway olmayan şirketler geride kalacak
- 🎯 Liderliğin stratejik yaklaşımı, developer productivity'yi belirleyen en kritik faktör
- 🎯 AI bir güçlendirici (amplifier), insan taleninin yerini alan bir araç değil

---

# Is Agentic Metadata the Next Infrastructure Layer?

**Kaynak:** [The New Stack](https://thenewstack.io/is-agentic-metadata-the-next-infrastructure-layer/)
**Etiketler:** `#agentic-ai` `#metadata` `#infrastructure` `#observability` `#ai-ops`

## TL;DR
AI ajanlar çalışırken zengin metadata üretiyor: reasoning trace'ler, tool call'lar, güven skorları. Bu veri henüz parçalı biçimde toplanıyor; oysa düzgün yönetilirse yeniden eğitim, compliance ve maliyet optimizasyonu için kritik kaynak.

## Ana Noktalar
- Gartner'a göre 2028'e kadar kurumsal uygulamaların 1/3'ü agentic AI içerecek
- Agentic metadata türleri:
  - **Operasyonel:** ID, timestamp, latency, token tüketimi
  - **Reasoning:** Düşünce adımları, karar güven skorları, hata kurtarma
  - **Etkileşim:** Tool call'lar, kaynak erişimleri, sorgu sıklığı
  - **Model:** Kullanılan modeller ve versiyonları
  - **Kullanıcı:** Promptlar, oturum bağlamı, insan düzeltmeleri
- Mevcut durum: "Çok parçalı bir görüntü" — çoğu ekip ad hoc yönetiyor
- Metadata, agent davranışını izlenebilir ve güvenilir hale getirir
- Reasoning metrikler, nihai sonuçtan çok "neden bu karar verildi?" sorusunu yanıtlıyor

## Anahtar Çıkarımlar
- 🎯 Agentic metadata, AI altyapısının bir sonraki kritik katmanı olmaya aday
- 🎯 Reasoning trace'leri toplamak, compliance ve retraining için zorunlu hale gelecek
- 🎯 Şu an parçalı olan bu alan, yakında standartlaşacak

---

# Harness Design for Long-Running Application Development

**Kaynak:** [Anthropic Engineering](https://www.anthropic.com/engineering/harness-design-long-running-apps)
**Etiketler:** `#claude` `#agent-harness` `#long-running-agents` `#multi-agent` `#frontend-design`

## TL;DR
Anthropic mühendisi, uzun süreli autonomous coding ve frontend tasarım kalitesini artırmak için GAN'lardan ilham alan bir planner-generator-evaluator mimarisi geliştirdi. Context sıfırlama ve harici değerlendirici kullanımı, agent performansını önemli ölçüde artırıyor.

## Ana Noktalar
- Naive implementasyonların iki temel sorunu:
  1. **Context anxiety:** Model context window dolunca işi erken bitiriyor
  2. **Self-evaluation bias:** Ajan kendi çıktısını sürekli övüyor, kaliteyi gerçekçi değerlendiremiyor
- **Çözüm: Context Reset** — context window tamamen temizleniyor, yapılandırılmış handoff artifact'ı ile yeni ajan devralıyor (compaction'dan daha etkili)
- **Frontend design için 4 gradleme kriteri:** Design quality, Originality, Craft, Functionality
- **GAN ilhamlı mimari:** Generator ajan + ayrı Evaluator ajan — harici geri bildirim döngüsü kaliteyi zorluyor
- **Final mimari:** Planner → Generator → Evaluator (3 ajan, çok saatlik autonomous oturumlar)
- Evaluator'ı kendi ürettiklerine karşı şüpheci yapılandırmak, generator'ı kendi çalışmasına karşı eleştirel yapmaktan çok daha kolay

## Anahtar Çıkarımlar
- 🎯 Uzun görevlerde context reset, compaction'dan üstün; temiz başlangıç "context anxiety"yi çözüyor
- 🎯 Özdeğerlendirme yanılgısını kırmak için görev ve değerlendirme ajanlarını ayırmak şart
- 🎯 Planner-Generator-Evaluator üçlüsü, tam yığın uygulama geliştirme için güçlü bir template

---

# Introducing Anthropic Interviewer: What 1,250 Professionals Told Us About Working with AI

**Kaynak:** [Anthropic Research](https://www.anthropic.com/research/anthropic-interviewer)
**Etiketler:** `#anthropic` `#ai-research` `#workforce` `#survey` `#societal-impact`

## TL;DR
Anthropic, Claude destekli otomatik mülakat aracı "Anthropic Interviewer" ile 1.250 profesyoneli (genel iş gücü, bilim insanları, yaratıcılar) sorguladı. Genel tablo iyimser: insanlar AI'ı güçlendirici buluyor, fakat kimlik kaygıları, eğitim entegrasyonu ve güvenlik endişeleri öne çıkıyor.

## Ana Noktalar
- **Genel iş gücü:** AI'ı rutin işleri delege etmek, profesyonel kimliği korumak için kullanmak istiyor; gelecekte AI denetim rolleri öngörülüyor
- **Yaratıcılar:** Prodüktivite artışından memnun ama meslektaş yargısı ve ekonomik yerinden edilme korkusu var; "AI işbirliğinin çoğu bir illüzyon"
- **Bilim insanları:** AI'nın hipotez üretmesini istiyor ama şu an yalnızca yazım ve kod hata ayıklamada kullanıyor; hallüsinasyon güvensizlik nedeni
- Kötümser konular: eğitimde entegrasyon, sanatçı yerinden edilmesi, güvenlik kaygıları, yazı bağımsızlığı
- İyimser konular: iş akışı otomasyonu, araştırma yardımı, müzik üretimi
- Tüm mülakat verileri halka açık yayınlandı (HuggingFace)

## Anahtar Çıkarımlar
- 🎯 Profesyoneller AI'ı güçlendirici görüyor; replacement korkusu hâlâ var ama çoğunluk iyimser
- 🎯 Yaratıcı topluluklar AI kullanımını "utanç verici" buluyor — sosyal baskı gerçek bir engel
- 🎯 Bilim insanları için asıl sorun güven: hallüsinasyon çözülmeden AI core research'e giremez

---

# Claude Code Advanced Patterns: Subagents, MCP, and Scaling to Real Codebases

**Kaynak:** [Anthropic Webinars](https://www.anthropic.com/webinars/claude-code-advanced-patterns)
**Etiketler:** `#claude-code` `#webinar` `#subagents` `#mcp` `#ci-cd`

## TL;DR
Claude Code'u bireysel kullanımdan ötesine taşımak isteyen ekipler için ileri düzey bir webinar. Subagent orkestrasyonu, MCP entegrasyonları ve büyük kod tabanlarında etkin context yönetimi ele alınıyor. 24 Mart 2026 tarihli kayıtlı etkinlik.

## Ana Noktalar
- Subagent'lar ve hook'lar ile multi-step işlerin orkestre edilmesi (babysitting gerektirmeden)
- MCP (Model Context Protocol) ile internal servislere bağlantı; custom tool ne zaman yazmalı
- Büyük repo'larda context yönetimi: monorepo için CLAUDE.md yapılandırma
- CI/CD entegrasyonu: otomatik PR review, test generation, regresyon yakalama
- Hedef kitle: Claude Code'u zaten kullanan, günlük iş akışlarına entegre etmek isteyen takımlar

## Anahtar Çıkarımlar
- 🎯 Subagent + hook kombinasyonu, Claude Code'u sıradan araçtan iş akışı orkestratörüne dönüştürüyor
- 🎯 MCP, Claude Code'u internal araçlara bağlamanın standart yolu
- 🎯 CI pipeline'a dahil etmek, insan review'ına geçmeden regresyon yakalamayı sağlıyor

---

# How to Transform Work with Claude for Excel and Claude for PowerPoint

**Kaynak:** [Anthropic Webinars](https://www.anthropic.com/webinars/claude-in-excel-and-powerpoint)
**Etiketler:** `#claude` `#excel` `#powerpoint` `#webinar` `#finance`

## TL;DR
Finans analistleri ve danışmanlar için tasarlanan webinar: Claude'un Excel ve PowerPoint entegrasyonlarıyla analist kalitesinde çıktıların nasıl hızla üretildiğini gösteriyor. RBC Capital Markets ve D.E. Shaw gibi kuruluşlardan gerçek kullanım örnekleri. 12 Şubat 2026 tarihli.

## Ana Noktalar
- Claude Opus 4.6, Cowork, Excel ve PowerPoint entegrasyonları duyuruldu
- Ham veriden publication-ready çıktıya saatler içinde ulaşmak mümkün (haftalar yerine)
- RBC Capital Markets ve D.E. Shaw gibi lider finans firmalarından uygulama örnekleri
- Finans analistleri, danışmanlar ve benzeri iş profilleri için kritik workflow iyileştirmeleri
- Hız, hassasiyet ve kalite: analist düzeyinde modelleme ve sunum hazırlığı

## Anahtar Çıkarımlar
- 🎯 Excel + PowerPoint entegrasyonu, knowledge worker iş akışlarını temelden değiştirecek
- 🎯 Finans sektörü, Claude'un kurumsal benimsenmesinde öncü alan olarak öne çıkıyor
- 🎯 "Haftalar değil saatler" vaadi gerçek kullanım örnekleriyle destekleniyor

---

# What We Shipped: Feature Updates, Tips, and Live Q&A with the Claude Code Team

**Kaynak:** [Anthropic Webinars](https://www.anthropic.com/webinars/what-we-shipped-feature-updates-tips-and-live-q-a-with-the-claude-code-team)
**Etiketler:** `#claude-code` `#webinar` `#product-updates` `#q-a`

## TL;DR
Claude Code ekibinin aylık düzenli webinar serisi. Son gönderilen özellikler, ekibin kendi workflow'larından pratik ipuçları ve canlı soru-cevap. 7 Nisan 2026 tarihli planlanmış etkinlik.

## Ana Noktalar
- Aylık "ne gönderdik" formatında Claude Code özet toplantısı
- Yeni özellikler ve neden inşa edildiklerine dair bağlam
- Ekibin günlük gerçek iş akışlarından pratik ipuçları ve tutorial'lar
- Canlı Q&A: ürünü inşa eden kişilerden doğrudan yanıtlar
- Konuşmacılar: Adam Wolff, Thariq Shihpar (Claude Code @ Anthropic)

## Anahtar Çıkarımlar
- 🎯 Anthropic, Claude Code için şeffaf ve düzenli ürün iletişimi kuruyor
- 🎯 Kullanıcı geri bildirimleri doğrudan ürün ekibine ulaşabiliyor
- 🎯 Pratik workflow ipuçları kadar "neden böyle yaptık" bağlamı da önemli

---

# Building Multi-Agent Applications with Deep Agents

**Kaynak:** [LangChain Blog](https://www.blog.langchain.com/building-multi-agent-applications-with-deep-agents/)
**Etiketler:** `#langchain` `#multi-agent` `#subagents` `#skills` `#context-management`

## TL;DR
LangChain'in Deep Agents framework'ü, iki temel primitive sunuyor: **subagent'lar** (izole bağlam yönetimi) ve **skill'ler** (kademeli yetenek ifşası). Bu ikili, context bloat problemini çözerken agent'ların yeteneklerini modüler şekilde genişletiyor.

## Ana Noktalar
- **Context bloat sorunu:** Agent bağlamı dolarsa performans düşüyor — "dumb zone" tehlikesi
- **Subagent'lar:** Ana agent'tan izole bağlamda çalışır; 20 tool call'ı içeride halleder, ana agent'a sadece özeti döner
- Subagent kullanım senaryoları: Context preservation, Specialization, Multi-model, Parallelization
- **Skill'ler:** SKILL.md dosyaları ile tanımlanır; açıklama pre-load edilir, içerik yalnızca gerektiğinde yüklenir
- Skills, agentskills.io spec'ini takip ediyor
- Subagent tanımında net description önemli: "Does finance stuff" ❌ vs. "Analyzes financial data..." ✅
- Tool set'ini minimize et: sadece gerekli araçları ver

## Anahtar Çıkarımlar
- 🎯 Subagent + Skill kombinasyonu, büyük görevlerde hem context hem yetenek yönetimini çözüyor
- 🎯 "General-purpose subagent" kavramı: aynı yeteneklerle sadece bağlamı izole etmek için bile kullanılabilir
- 🎯 AgentSkills.io spec'i, cross-framework skill taşınabilirliği için standartlaşıyor

---

# The Guy Who Coined 'Vibe-Coding' Says the Next Big Thing Is 'Agentic Engineering'

**Kaynak:** [Business Insider](https://www.businessinsider.com/agentic-engineering-andrej-karpathy-vibe-coding-2026-2)
**Etiketler:** `#agentic-engineering` `#vibe-coding` `#andrej-karpathy` `#ai-coding` `#future-of-software`

## TL;DR
Vibe-coding teriminin yaratıcısı Andrej Karpathy, terimin 1. yılında yeni bir kavram ortaya koydu: "agentic engineering". Vibe-coding'de insan AI'ya kod yazdırırken, agentic engineering'de AI agent'ları kendi kendine kod yazıyor. Burada hem sanat hem bilim hem de uzmanlık var.

## Ana Noktalar
- **Vibe-coding:** İnsan → AI'a prompt → AI kod yazar
- **Agentic engineering:** AI agent'ları bağımsız olarak kod yazar; insan daha çok yönlendirici konumunda
- Karpathy "agentic engineering" adını tercih ediyor çünkü bu işte "sanat, bilim ve uzmanlık" var
- Vibe-coding pazarı patlamaya devam ediyor: Lovable ($6.6B valuation), Cursor ($2.3B Series D, $1B+ ARR)
- 167 yazılım mühendisi anketi: 75 "ayak uyduruyor", 30 "önde", 27 "geride"
- Karpathy: OpenAI kurucu üyesi → Tesla Autopilot → Eureka Labs (AI-native okul)

## Anahtar Çıkarımlar
- 🎯 Agentic engineering, vibe-coding'in bir sonraki evrimi — insan daha az kod yazıyor, agent'lar tamamen özerk
- 🎯 Bu geçiş, yazılım mühendisliği mesleğini köklü biçimde dönüştürüyor
- 🎯 Vibe-coding pazarının hızı (Lovable, Cursor gibi devler) agentic engineering'in kaçınılmaz olduğunu gösteriyor

---

## REPORT

| # | Link | Durum |
|---|------|-------|
| 1 | thenewstack.io — AI merging with platform engineering | ✅ İşlendi |
| 2 | thenewstack.io — Agentic metadata next infrastructure | ✅ İşlendi |
| 3 | anthropic.com — Harness design long-running apps | ✅ İşlendi |
| 4 | anthropic.com — Anthropic Interviewer research | ✅ İşlendi |
| 5 | anthropic.com — Claude Code Advanced Patterns webinar | ✅ İşlendi |
| 6 | anthropic.com — Claude in Excel and PowerPoint webinar | ✅ İşlendi |
| 7 | anthropic.com — What We Shipped webinar | ✅ İşlendi |
| 8 | langchain.com — Multi-agent with Deep Agents | ✅ İşlendi |
| 9 | businessinsider.com — Agentic engineering Karpathy | ✅ İşlendi |
| 10 | forbes.com — The agentic layer enterprise SaaS | ❌ SKIP (403 — engel) |
| 11 | forbes.com — Rust vibe coding era | ❌ SKIP (403 — engel) |

**Toplam işlenen: 9 | Skip: 2**
**Skip listesi:** Forbes #10, Forbes #11 (her ikisi de 403 erişim engeli — JS/ad-blocker zorunlu)
