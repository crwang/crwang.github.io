---
permalink: "/resources/"
layout: page_index
title:  "Resources"
---

<ul>
{% for node in site.pages %}
    {% if node.url contains "/resources/" and node.url != "/resources/"%}
    <li><a href="{{node.url}}">{{node.title }}</a></li>
    {% endif %}
{% endfor %}
</ul>