---
layout: page
show_meta: false
title: "Cours Linux"
header:
   image_fullwidth: "header_unsplash_5.jpg"
permalink: "/cours_linux/"
categories:
    - linux
breadcrumb: true
---
<ul>
    {% for post in site.categories.cours_linux %}
    <li><a href="{{ site.url }}{{ post.url }}">{{ post.title }}</a></li>
    {% endfor %}
</ul>
