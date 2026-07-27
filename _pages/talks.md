---
layout: default
title: "Talks & Posters"
permalink: /talks/
description: "Talks, presentations, and posters by Kenechukwu Nwodo."
---

<h1 class="page-title">Talks &amp; Posters</h1>

<h2>Talks</h2>
{% assign talks = site.talks | sort: "date" | reverse %}
{% for t in talks %}
<article class="talk">
  <div class="talk__kicker">Talk</div>
  {% if t.link and t.link != "" %}
    <a class="talk__title" href="{{ t.link }}" target="_blank" rel="noopener">{{ t.title }}</a>
  {% else %}
    <p class="talk__title">{{ t.title }}</p>
  {% endif %}
  <div class="talk__meta"><span class="venue">{{ t.venue }}</span>{% if t.location %} &middot; {{ t.location }}{% endif %}</div>
  <div class="talk__when">{{ t.date | date: "%B %-d, %Y" }}</div>
</article>
{% endfor %}

<h2>Posters</h2>
{% assign posters = site.posters | sort: "date" | reverse %}
{% for p in posters %}
<article class="talk">
  <div class="talk__kicker">Poster</div>
  {% if p.link and p.link != "" %}
    <a class="talk__title" href="{{ p.link }}" target="_blank" rel="noopener">{{ p.title }}</a>
  {% else %}
    <p class="talk__title">{{ p.title }}</p>
  {% endif %}
  <div class="talk__meta"><span class="venue">{{ p.venue }}</span>{% if p.location %} &middot; {{ p.location }}{% endif %}</div>
  <div class="talk__when">{{ p.date | date: "%B %-d, %Y" }}</div>
  {% comment %} Find a PDF in /files/posters/ whose name matches this poster's filename slug {% endcomment %}
  {% assign slug = p.path | split: "/" | last | remove: ".md" %}
  {% assign pdf = site.static_files | where_exp: "f", "f.path contains '/files/posters/'" | where_exp: "f", "f.basename == slug" | first %}
  {% if pdf %}
  <a class="poster-link" href="{{ pdf.path | relative_url }}" target="_blank" rel="noopener">
    <svg viewBox="0 0 24 24" aria-hidden="true"><path d="M6 2a2 2 0 0 0-2 2v16a2 2 0 0 0 2 2h12a2 2 0 0 0 2-2V8l-6-6H6zm7 1.5L18.5 9H13V3.5zM8 13h8v1.5H8V13zm0 3h8v1.5H8V16z"/></svg>
    View poster (PDF)
  </a>
  {% endif %}
</article>
{% endfor %}
