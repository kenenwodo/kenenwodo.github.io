---
layout: default
title: "Publications"
permalink: /publications/
description: "Peer-reviewed papers, book chapters, and thesis by Kenechukwu Nwodo."
---

<h1 class="page-title">Publications</h1>

{% assign order = "Conference Papers,Book Chapters,Thesis" | split: "," %}
{% for cat in order %}
  {% if cat == "Conference Papers" %}
    {% assign confs = site.publications | where: "category", "Conference Papers" %}
    {% assign reviews = site.publications | where: "category", "Under Review" %}
    {% assign items = confs | concat: reviews | sort: "order" %}
  {% else %}
    {% assign items = site.publications | where: "category", cat | sort: "order" %}
  {% endif %}
  {% if items.size > 0 %}
<h2>{{ cat }}</h2>
<ol class="pub-list">
  {% for pub in items %}
  <li class="pub">
    <span class="pub__num"></span>
    <div>
      {% if pub.link and pub.link != "" %}
        <a class="pub__title" href="{{ pub.link }}" target="_blank" rel="noopener">{{ pub.title }}</a>
      {% else %}
        <p class="pub__title">{{ pub.title }}</p>
      {% endif %}
      <p class="pub__authors">{{ pub.authors | markdownify | remove: '<p>' | remove: '</p>' | strip | replace: '<strong>', '<span class="me">' | replace: '</strong>', '</span>' }}{% if pub.note %} <em>({{ pub.note }})</em>{% endif %}</p>
      <p class="pub__venue">{{ pub.venue }} &middot; <span class="year">{{ pub.year }}</span>{% if pub.category == "Under Review" %}<span class="badge badge--review">Under Review</span>{% elsif pub.category == "Book Chapters" %}<span class="badge badge--chapter">Chapter</span>{% endif %}</p>
    </div>
  </li>
  {% endfor %}
</ol>
  {% endif %}
{% endfor %}
