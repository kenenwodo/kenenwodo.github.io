---
layout: default
title: "Service"
permalink: /service/
description: "Professional service, teaching, and affiliations of Kenechukwu Nwodo."
---

<h1 class="page-title">Service</h1>

{% assign groups = "Review,Teaching,Volunteering,Award" | split: "," %}
{% assign labels = "Reviewing,Teaching,Volunteering,Awards &amp; Grants" | split: "," %}
{% for cat in groups %}
  {% assign items = site.service | where: "category", cat | sort: "order" %}
  {% if items.size > 0 %}
<div class="svc-group">
<h2>{{ labels[forloop.index0] }}</h2>
<ul class="svc-list">
  {% for s in items %}
  <li>
    <span class="svc__what"><strong>{{ s.what }}</strong>{% if s.org %} <span class="org">— {{ s.org }}</span>{% endif %}</span>
    <span class="svc__year">{{ s.year }}</span>
  </li>
  {% endfor %}
</ul>
</div>
  {% endif %}
{% endfor %}

{% assign affils = site.service | where: "category", "Affiliation" | sort: "order" %}
{% if affils.size > 0 %}
<div class="svc-group">
<h2>Affiliations</h2>
<p class="affil-line">{% for a in affils %}{{ a.org }}{% if a.what %} {{ a.what }}{% endif %}{% unless forloop.last %}, {% endunless %}{% endfor %}</p>
</div>
{% endif %}
