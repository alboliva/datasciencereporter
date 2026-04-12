---
layout: page
title: Pubblicazioni Anno 2026
permalink: /2026/
---

## Filtra per Argomento
{% assign argomenti = site.data.pubblicazioni | map: "argomento" | uniq | sort %}
<p>
  <a href="/2026/">Tutti</a>
  {% for arg in argomenti %}
  · <a href="/2026/argomento/{{ arg | slugify }}/">{{ arg }}</a>
  {% endfor %}
</p>

## Filtra per Tag
{% assign tags = site.data.pubblicazioni | map: "tag" | uniq | sort %}
<p>
  {% for tag in tags %}
  <a href="/2026/tag/{{ tag | downcase }}/" 
     style="background:#eee; padding:2px 8px; border-radius:4px; margin:2px; font-size:0.85em;">
    #{{ tag }}
  </a>
  {% endfor %}
</p>

---

## Elenco Cronologico
{% assign sorted_pubs = site.data.pubblicazioni | sort: "data" | reverse %}
<ul>
  {% for pub in sorted_pubs %}
  <li>
    <strong>{{ pub.titolo }}</strong><br>
    <small>{{ pub.data_label }}</small> —
    <a href="{{ pub.link }}">Leggi l'articolo</a><br>
    <a href="/2026/argomento/{{ pub.argomento | slugify }}/">{{ pub.argomento }}</a>
    <a href="/2026/tag/{{ pub.tag | downcase }}/" 
       style="color:gray; font-size:0.85em;">#{{ pub.tag }}</a>
  </li>
  {% endfor %}
</ul>