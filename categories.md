---
layout: default
title: "Kategoriler"
---

# Kategoriler

{% assign categories = site.summaries | map: "category" | uniq | sort %}
{% for cat in categories %}

<h2 id="{{ cat | slugify }}">{{ cat }}</h2>

{% assign items = site.summaries | where: "category", cat | sort: "date" | reverse %}
{% for summary in items %}
<div class="card">
  <a href="{{ summary.url | relative_url }}">
    <div class="card-title">{{ summary.title }}</div>
    <div class="card-meta">
      {% if summary.date %}📅 {{ summary.date | date: "%Y-%m-%d" }}{% endif %}
      {% if summary.type %} · <span class="badge">{{ summary.type }}</span>{% endif %}
    </div>
  </a>
</div>
{% endfor %}

{% endfor %}
