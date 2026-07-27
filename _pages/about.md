---
layout: default
title: "About"
permalink: /
description: "Kenechukwu Nwodo — Computer Engineering PhD Candidate at Virginia Tech working on agentic AI for autonomous cyber defense and LLM-driven vulnerability management."
---

<h2>About Me</h2>
<section class="about">
<p>I am a Computer Engineering Ph.D. Candidate at <a href="https://www.vt.edu">Virginia Tech</a>, in the <a href="https://nss.ece.vt.edu/">Network and Systems Security Lab</a>, supervised by <a href="https://nss.ece.vt.edu/angelos/">Professor Angelos Stavrou</a> and <a href="https://ece.vt.edu/people/profile/wangh.html">Professor Haining Wang</a>. I am conducting research on securing software systems and autonomous network defense.</p>

<p>My research focuses on agentic AI for autonomous cyber defense and LLM-driven vulnerability management, alongside industry experience in mobile security static analysis. I evaluate defender/attacker cyber agents across simulation and emulation, and use large language models to make vulnerability analysis easier to automate.</p>
</section>

<h2>Education</h2>
<ul class="edu">
  <li>
    <span class="edu__degree">Ph.D. in Computer Engineering<br><span class="edu__school">Virginia Tech</span></span>
    <span class="edu__years">2020 &ndash; Dec. 2026 (exp.)</span>
  </li>
  <li>
    <span class="edu__degree">M.S. in Computer Engineering<br><span class="edu__school">Virginia Tech</span></span>
    <span class="edu__years">2020 &ndash; 2023</span>
  </li>
  <li>
    <span class="edu__degree">B.S. in Electrical Engineering<br><span class="edu__school">Rensselaer Polytechnic Institute</span></span>
    <span class="edu__years">2016 &ndash; 2020</span>
  </li>
</ul>

<h2>News</h2>
<ul class="news">
  {% assign news = site.data.news | sort: "order" %}
  {% for item in news %}
  <li>
    <span class="news__date">{{ item.date }}</span>
    {{ item.text | markdownify | remove: '<p>' | remove: '</p>' | strip }}
  </li>
  {% endfor %}
</ul>
