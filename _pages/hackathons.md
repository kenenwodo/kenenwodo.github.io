---
layout: default
title: "Hackathon Projects"
permalink: /hackathons/
description: "Projects Kenechukwu Nwodo built at hackathons, separate from his Ph.D. research."
---

<h1 class="page-title">Hackathon Projects</h1>

<p class="page-intro">Projects I built at hackathons, separate from my Ph.D. research. For my research, see <a href="{{ '/research/' | relative_url }}">Research</a> and <a href="{{ '/publications/' | relative_url }}">Publications</a>.</p>

{% assign items = site.hackathons | sort: "date" | reverse %}
{% for p in items %}
<article class="talk project">
  <p class="talk__title">{{ p.title }}</p>
  <div class="talk__meta"><span class="venue">{% if p.event_link %}<a href="{{ p.event_link }}" target="_blank" rel="noopener">{{ p.event }}</a>{% else %}{{ p.event }}{% endif %}</span></div>
  <div class="talk__when">{{ p.date | date: "%B %Y" }}</div>
  <div class="talk__body">{{ p.content | markdownify }}</div>
  {% if p.tools %}<p class="project__tools"><span class="project__tools-label">Tools</span> {{ p.tools }}</p>{% endif %}
  {% if p.link and p.link != "" %}
  <a class="poster-link" href="{{ p.link }}" target="_blank" rel="noopener">
    <svg viewBox="0 0 24 24" aria-hidden="true"><path d="M12 2A10 10 0 0 0 8.8 21.5c.5.1.68-.22.68-.48v-1.7c-2.78.6-3.37-1.34-3.37-1.34-.45-1.16-1.1-1.47-1.1-1.47-.9-.62.07-.6.07-.6 1 .07 1.53 1.03 1.53 1.03.9 1.52 2.34 1.08 2.9.83.1-.65.35-1.09.63-1.34-2.22-.25-4.56-1.11-4.56-4.94 0-1.09.39-1.98 1.03-2.68-.1-.26-.45-1.27.1-2.65 0 0 .84-.27 2.75 1.02a9.5 9.5 0 0 1 5 0c1.9-1.29 2.74-1.02 2.74-1.02.55 1.38.2 2.39.1 2.65.64.7 1.03 1.59 1.03 2.68 0 3.84-2.34 4.68-4.57 4.93.36.31.68.92.68 1.85v2.74c0 .27.18.59.69.48A10 10 0 0 0 12 2z"/></svg>
    View on GitHub
  </a>
  {% endif %}
</article>
{% endfor %}
