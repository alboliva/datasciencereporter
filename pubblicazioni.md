---
layout: page
title: Pubblicazioni Anno 2026
permalink: /2026/
---
## Elenco Cronologico

{% assign sorted_pubs = site.data.pubblicazioni | sort: "data" | reverse %}
<ul>
  {% for pub in sorted_pubs %}
  <li>
    <strong>{{ pub.titolo }}</strong><br>
    {% if pub.titolo_en %}
    <small style="color: #888; font-style: italic;">{{ pub.titolo_en }}</small><br>
    {% endif %}
    <small>{{ pub.data_label }}</small> —
    <a href="{{ pub.link }}">Leggi l'articolo</a>
    {% if pub.link_en and pub.link_en != "" %}
    · <a href="{{ pub.link_en }}" style="color: #555;">EN</a>
    {% endif %}
    <small style="color: gray;">#{{ pub.tag }}</small>
  </li>
  {% endfor %}
</ul>