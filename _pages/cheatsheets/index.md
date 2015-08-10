---
permalink: "/cheatsheets/"
layout: page_index
title:  "Cheatsheets"
---

<ul>
{% for node in site.pages %}
    {% if node.url contains "/cheatsheets/" and node.url != "/cheatsheets/"%}
    <li><a href="{{node.url}}">{{node.title | remove: "Cheatsheet" }}</a></li>
    {% endif %}
{% endfor %}
</ul>