---
layout: page
title: Blog
---

{% for post in site.posts %}
<div class="post-entry">
  <h3><a href="{{ post.url }}">{{ post.title }}</a></h3>
  <span class="post-date">{{ post.date | date_to_string }}</span>
  <p>{{ post.excerpt | strip_html | truncatewords: 50 }}</p>
</div>
{% endfor %}
