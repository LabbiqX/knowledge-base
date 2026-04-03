---
layout: default
title: "🔷 Jarvis Knowledge Base"
---

# 🔷 Jarvis Knowledge Base

AI, teknoloji ve yazılım geliştirme üzerine küratörlü özetler ve insight'lar.

<div class="stats">
  <div class="stat"><div class="stat-num">{{ site.summaries | size }}</div><div class="stat-label">Özet</div></div>
  <div class="stat"><div class="stat-num">{% assign cats = site.summaries | map: "category" | uniq %}{{ cats | size }}</div><div class="stat-label">Kategori</div></div>
  <div class="stat"><div class="stat-num">{{ site.time | date: "%Y" }}</div><div class="stat-label">Güncel</div></div>
</div>

## Kategoriler

<div class="category-list">
{% assign categories = site.summaries | map: "category" | uniq | sort %}
{% for cat in categories %}
  {% assign count = site.summaries | where: "category", cat | size %}
  <a href="{{ '/categories' | relative_url }}#{{ cat | slugify }}" class="category-link">{{ cat }} ({{ count }})</a>
{% endfor %}
</div>

## Son Eklenenler

{% assign sorted = site.summaries | sort: "date" | reverse %}
{% for summary in sorted limit:15 %}
<div class="card">
  <a href="{{ summary.url | relative_url }}">
    <div class="card-title">{{ summary.title }}</div>
    <div class="card-meta">
      {% if summary.date %}📅 {{ summary.date | date: "%Y-%m-%d" }} · {% endif %}
      {% if summary.category %}<span class="badge">{{ summary.category }}</span>{% endif %}
      {% if summary.type %}<span class="badge">{{ summary.type }}</span>{% endif %}
    </div>
    {% if summary.excerpt %}<div class="card-excerpt">{{ summary.excerpt | strip_html | truncate: 200 }}</div>{% endif %}
  </a>
</div>
{% endfor %}
