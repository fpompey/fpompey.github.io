---
layout: page
show_meta: false
title: "Procédure"
header:
   image_fullwidth: "header_unsplash_5.jpg"
permalink: "/procedure/"
---
<ul>
    {% for post in site.categories.procedure %}
    <li><a href="{{ site.url }}{{ post.url }}">{{ post.title }}</a></li>
    {% endfor %}
</ul>

