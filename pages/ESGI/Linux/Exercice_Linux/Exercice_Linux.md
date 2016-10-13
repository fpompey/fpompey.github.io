---
layout: page
show_meta: false
title: "Exercice linux"
header:
   image_fullwidth: "header_unsplash_5.jpg"
permalink: "/ESGI/Linux/Exercice_Linux/"
breadcrumb: true
---
<ul>
    {% for post in site.categories.ESGI/Linux/Exercice_Linux %}
    <li><a href="{{ site.url }}{{ post.url }}">{{ post.title }}</a></li>
    {% endfor %}
</ul>
