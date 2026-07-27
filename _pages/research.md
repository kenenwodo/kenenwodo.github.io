---
layout: default
title: "Research"
permalink: /research/
description: "Research areas of Kenechukwu Nwodo: autonomous cyber agents, software vulnerability management, and SCADA/IoT security."
---

<h1 class="page-title">Research</h1>

{% assign topics = site.research | sort: "order" %}
{% for t in topics %}
<article class="topic">
  <h2 class="topic__title">{{ t.title }}</h2>
  <div class="topic__body">{{ t.content | markdownify }}</div>
</article>
{% endfor %}
