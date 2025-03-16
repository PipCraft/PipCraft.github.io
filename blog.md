---
layout: default
title: Blog
permalink: /blog/
---

<h1>Welcome to My Blog</h1>

<p>Here are all the latest posts:</p>

<div class="blog-posts">
  {% for post in site.posts %}
    <article class="blog-post">
      <h2><a href="{{ post.url }}">{{ post.title }}</a></h2>
      <p><strong>Published on:</strong> {{ post.date | date: "%B %d, %Y" }}</p>
      <p class="excerpt">{{ post.excerpt | truncate: 100 }}</p>
      <a href="{{ post.url }}">Read More</a>
    </article>
  {% endfor %}
</div>
