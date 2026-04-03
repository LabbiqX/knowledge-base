---
layout: summary
title: "Best Practices for Coding with Agents (Cursor)"
date: 2026-03-29
source: "https://cursor.com/blog/agent-best-practices"
category: "AI Coding Tools"
type: "Makale"
---

## TL;DR
Cursor'un resmi agent best practices rehberi. Temel mesaj: plan yap sonra kodla, context'i yönet, agent'ı Rules ve Skills ile genişlet, TDD ile çalış. Agent harness kavramı önemli — her model farklı tuning ister, Cursor bunu otomatik yapıyor. Uzun konuşmalar gürültü biriktirir, yeni conversation başlatmayı bil.

---

## Agent Harness Kavramı
- Üç bileşen: Instructions (system prompt), Tools (dosya düzenleme, arama, terminal), Model
- Her model farklı promptlara farklı tepki verir — Cursor model bazlı harness tuning yapıyor
- Kullanıcı model seçer, harness optimizasyonu otomatik

## Plan First
- Plan Mode (Shift+Tab): kod yazmadan önce araştır, soru sor, plan oluştur, onay al
- Chicago Üniversitesi çalışması: deneyimli geliştiriciler önce plan yapar
- Plan onaylandıktan sonra agent çalışır
- Agent yanlış yöne giderse: değişiklikleri geri al, planı düzenle, tekrar çalıştır (follow-up prompt'tan hızlı)

## Context Yönetimi
- **Agent'ın bulmasına izin ver** — her dosyayı manuel etiketleme gereksiz, semantic + grep arama güçlü
- **Yeni conversation ne zaman:** farklı task, agent karışık, bir iş birimi tamamlandı
- **Devam ne zaman:** aynı feature üzerinde iterasyon, önceki bağlam lazım, hemen debug
- **@Past Chats:** önceki konuşmalardan seçici referans — tüm konuşmayı kopyalamaktan iyi
- **@Branch:** mevcut çalışma bağlamı için

## Agent Genişletme
- **Rules (.cursor/rules/):** Statik context — her konuşmada dahil. Komutlar, kod stili, iş akışı. Git'e commit'le.
- **Skills (SKILL.md):** Dinamik yetenekler — agent gerekli gördüğünde yükler. Custom komutlar, hook'lar, domain bilgisi.
- **Hooks:** Agent eylemleri öncesi/sonrası çalışan script'ler — grind pattern (testler geçene kadar iterasyon)

## TDD Pattern
1. Test yaz (beklenen input/output, mock implementasyon YOK)
2. Testlerin fail ettiğini doğrula (implementasyon kodu yazma)
3. Testleri commit'le
4. Agent'a testleri geçecek kod yazdır (testleri değiştirme)
5. İmplementasyonu commit'le

## Diğer İş Akışları
- **/pr komutu:** diff bak → commit mesajı yaz → push → PR aç
- **/fix-issue:** Issue detaylarını çek → ilgili kodu bul → düzelt → PR aç
- **Görsel debugging:** Screenshot yapıştır, agent incelesin — kelimelerle anlatmaktan hızlı
- **Codebase learning:** "Loglama nasıl çalışıyor?" gibi sorularla onboarding

## Code Review
- **Generation sırasında:** Diff izle, yanlış yöne giderse Stop
- **Agent Review:** Bitince "Find Issues" — satır satır analiz
- **Bugbot:** PR'lara otomatik review

---

## 🎯 Anahtar Çıkarım
> En etkili coding agent kullanımı "plan → execute → review" döngüsüne dayanıyor. Agent'a context verme sanatı yeni geliştiricinin en kritik becerisi. Rules dosyaları git'e commit'lenmeli ki tüm takım aynı agent davranışından faydalansın — bu "agent engineering" in pratik karşılığı.
