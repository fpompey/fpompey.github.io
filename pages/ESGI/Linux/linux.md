---
layout: page
show_meta: false
title: "Linux"
header:
   image_fullwidth: "header_unsplash_5.jpg"
permalink: "/esgi/linux/"
categories:
    - esgi
breadcrumb: true
---
<ul>
    {% for post in site.categories.linux %}
    <li><a href="{{ site.url }}{{ post.url }}">{{ post.title }}</a></li>
    {% endfor %}
</ul>
