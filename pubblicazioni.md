---
layout: page
title: Pubblicazioni Anno 2026
permalink: /2026/
---

<style>
  .nav-tabs { display: flex; gap: 10px; margin-bottom: 20px; border-bottom: 1px solid #ddd; padding-bottom: 10px; }
  .tab-btn { padding: 8px 16px; cursor: pointer; border-radius: 5px; border: 1px solid #ccc; background: #f9f9f9; text-decoration: none; color: black; font-weight: bold; }
  .tab-btn:hover { background: #eee; }
  .pub-card { border-left: 4px solid #007bff; padding: 10px; margin-bottom: 15px; background: #fff; box-shadow: 0 2px 4px rgba(0,0,0,0.05); }
  .group-title { color: #007bff; border-bottom: 1px solid #eee; margin-top: 30px; }
</style>

<div class="nav-tabs">
  <a href="#anno" class="tab-btn">Per Anno</a>
  <a href="#tag" class="tab-btn">Per Tag</a>
  <a href="#argomento" class="tab-btn">Per Argomento</a>
</div>

<div id="anno">
  <h2 class="group-title">Organizzate per Anno</h2>
  {% assign by_year = site.data.pubblicazioni | group_by: "anno" | sort: "name" | reverse %}
  {% for year in by_year %}
    ### {{ year.name }}
    {% for pub in year.items %}
      <div class="pub-card">
        <strong>{{ pub.titolo }}</strong><br>
        <em>{{ pub.rivista }}</em> | <a href="{{ pub.link }}">Link</a>
      </div>
    {% endfor %}
  {% endfor %}
</div>

<hr>

<div id="tag">
  <h2 class="group-title">Organizzate per Tag</h2>
  {% assign by_tag = site.data.pubblicazioni | group_by: "tag" %}
  {% for tag in by_tag %}
    ### {{ tag.name | capitalize }}
    {% for pub in tag.items %}
      <div class="pub-card">
        <strong>{{ pub.titolo }}</strong> ({{ pub.anno }})
      </div>
    {% endfor %}
  {% endfor %}
</div>

<hr>

<div id="argomento">
  <h2 class="group-title">Per Argomento</h2>
  {% assign by_topic = site.data.pubblicazioni | group_by: "argomento" %}
  {% for topic in by_topic %}
    ### {{ topic.name }}
    {% for pub in topic.items %}
      <div class="pub-card">
        <strong>{{ pub.titolo }}</strong> — {{ pub.rivista }}
      </div>
    {% endfor %}
  {% endfor %}
</div>