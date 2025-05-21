---
layout: default
title: Coffee Index
permalink: /coffee/
---

<h1>Coffee Index</h1>
<p>Browse beans, brewers, and equipment I’ve tried and tested:</p>

<div class="coffee-grid">
  {% for item in site.coffee %}
    <article class="coffee-card">
      {% if item.image %}
        <img src="{{ item.image }}" alt="{{ item.title }}" class="coffee-thumbnail">
      {% endif %}
      <h3><a href="{{ item.url }}">{{ item.title }}</a></h3>
      <p><strong>Type:</strong> {{ item.type }}</p>
      {% if item.roast %}<p><strong>Roast:</strong> {{ item.roast }}</p>{% endif %}
      {% if item.brew %}<p><strong>Brew Method:</strong> {{ item.brew }}</p>{% endif %}
      {% if item.rating %}<p><strong>Rating:</strong> ⭐ {{ item.rating }}/5</p>{% endif %}
    </article>
  {% endfor %}
</div>
