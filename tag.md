---
layout: page
permalink: /2026/tag/:slug/
---

{% assign tag_corrente = page.url | split: "/" | last %}
{% assign filtered = site.data.pubblicazioni | where: "tag" | downcase == tag_corrente %}

## Articoli con tag: #{{ tag_corrente }}

{% assign sorted = filtered | sort: "data" | reverse %}
<ul>
  {% for pub in sorted %}
  <li>
    <strong>{{ pub.titolo }}</strong><br>
    <small>{{ pub.data_label }}</small> —
    <a href="{{ pub.link }}">Leggi l'articolo</a>
  </li>
  {% endfor %}
</ul>
<p><a href="/2026/">← Torna a tutte le pubblicazioni</a></p>