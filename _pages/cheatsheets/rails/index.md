---
permalink: "/cheatsheets/rails/"
layout: page_index
title:  "Rails Cheatsheet"
---

<ol class="breadcrumb">
  <li><a href="/cheatsheets">Cheatsheets</a></li>
  <li>Rails</li>
</ol>

<ul>
{% for node in site.pages %}
    {% if node.url contains "/cheatsheets/rails/" and node.url != "/cheatsheets/rails/"%}
    <li><a href="{{node.url}}">{{node.title }}</a></li>
    {% endif %}
{% endfor %}
</ul>
