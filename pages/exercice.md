---
layout: page
show_meta: false
title: "Exercices"
header:
   image_fullwidth: "header_unsplash_5.jpg"
permalink: "/exercice/"
breadcrumb: true
---
<ul>
    {% for post in site.categories.exercice %}
    <li><a href="{{ site.url }}{{ post.url }}">{{ post.title }}</a></li>
    {% endfor %}
</ul>
