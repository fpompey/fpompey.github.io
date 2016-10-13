---
layout: page
show_meta: false
title: "Exercice linux"
header:
   image_fullwidth: "header_unsplash_5.jpg"
permalink: "/esgi/linux/exercice_linux/"
categories:
    - linux
breadcrumb: true
---
<ul>
    {% for post in site.categories.exercice_linux %}
    <li><a href="{{ site.url }}{{ post.url }}">{{ post.title }}</a></li>
    {% endfor %}
</ul>
