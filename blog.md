---
layout: default
title: Blog
permalink: /blog/
---
<div class="container blog-index-container">
<div class="post-list">
  {% for post in site.categories.blog %}

    <article class="blog-listing">
      <h3>
        <a class="post-link" href="{{ post.url | relative_url }}">{{ post.title | escape }}</a>
      </h3>
      {% assign date_format = site.minima.date_format | default: "%b %-d, %Y" %}
      <span class="post-meta">{{ post.date | date: date_format }}</span>
      {% if post.image %}
      <img src="{{site.url}}{{post.image}}" clas="blog-image">
      {% endif %}
      {{ post.content | split:'<!--break-->' | first }}
        {% if post.content contains '<!--break-->' %}
          <a href="{{ post.url }}">read more</a>
       {% endif %}
    </article>
  {% endfor %}
</div>
</div>
