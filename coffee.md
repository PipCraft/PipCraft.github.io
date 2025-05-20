---
layout: default
title: Coffee Index
permalink: /coffee/
---

<h1>Coffee Index</h1>

<ul>
  {% for item in site.coffee %}
    <li>
      <a href="{{ item.url }}">{{ item.title }}</a>
      – {{ item.type }} – {{ item.roast }} – ⭐ {{ item.rating }}
    </li>
  {% endfor %}
</ul>
