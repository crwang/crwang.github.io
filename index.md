---
layout: page_index
title: Tech stuff!
tagline:
description: Tech Space for storing and sharing programming notes
---

{% include JB/setup %}

This site is aimed at sharing tech resources and insights that I have found useful. 

As a tech person, I've decided to use a personal url, not because I'm vain (or I try not to be), but because it keeps from offending or misrespresenting companies and it's a way to share my knowledge/expertise.
    
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



