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
    <small>{{ pub.data | date: "%d %B %Y" }}</small> —
    <a href="{{ pub.link }}">Leggi l'articolo</a>
    <small style="color: gray;">#{{ pub.tag }}</small>
  </li>
  {% endfor %}
</ul>