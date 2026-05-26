---
layout: default
title: Blog
bg_class: bg-barbican
permalink: /blog/
---

<h1>Welcome to My Blog</h1>
<p>Here are all the latest posts:</p>

<div class="blog-posts">
  {% assign postsByYear = site.posts | group_by_exp: "post", "post.date | date: '%Y'" %}
  {% comment %} 
    If the line above still acts up on your local setup, 
    use this alternate bulletproof syntax instead:
    {% assign postsByYear = site.posts | group_by_exp: "item", "item.date.year" %}
  {% endcomment %}

  {% for year in postsByYear %}
    <h2>{{ year.name }}</h2>
    {% for post in year.items %}
      <article class="blog-post">
        {% if post.image %}
          <img src="{{ post.image | relative_url }}" alt="{{ post.title }} thumbnail" class="post-thumbnail">
        {% endif %}
        <h3><a href="{{ post.url | relative_url }}">{{ post.title }}</a></h3>
        <p><strong>Published:</strong> {{ post.date | date: "%B %d, %Y" }}</p>
        
        {% assign words = post.content | number_of_words %}
        {% assign minutes = words | divided_by: 200.0 %}
        <p><em>~{{ minutes | ceil }} min read</em></p>
        
        <p class="excerpt">{{ post.excerpt | strip_html | truncatewords: 20 }}</p>

        {% if post.tags %}
          <p class="tags">
            {% for tag in post.tags %}
              <span class="tag">{{ tag }}</span>
            {% endfor %}
          </p>
        {% endif %}
        <a href="{{ post.url | relative_url }}">Read More →</a>
      </article>
    {% endfor %}
  {% endfor %}
</div>
