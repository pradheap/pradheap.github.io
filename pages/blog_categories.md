---
layout: default
title: "A list of Categories"
permalink: "/category/"
---

<ul>
  {% for category in site.blog_categories %}
    <li>
      <a href="{{ category.url }}">{{ category.title }}</a>
      - {{ category.headline }}
    </li>
  {% endfor %}
</ul>