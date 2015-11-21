---
layout: default_home
title: Tech Blog & Resources
tagline:
description: Tech Space for storing and sharing programming notes
---

{% include JB/setup %}

This site is aimed at sharing tech resources and insights that I have found useful.

### Recent Posts
<ul class="posts">
  {% for post in site.posts limit:10 %}
    <li><span>{{ post.date | date_to_string }}</span> &raquo; <a href="{{ BASE_PATH }}{{ post.url }}">{{ post.title }}</a></li>
  {% endfor %}
</ul>

{% if site.posts > 10 %}
### Older Posts
<ul class="posts">
  {% for post in site.posts offset:10 limit:10 %}
    <li><span>{{ post.date | date_to_string }}</span> &raquo; <a href="{{ BASE_PATH }}{{ post.url }}">{{ post.title }}</a></li>
  {% endfor %}
</ul>
{% endif %}



