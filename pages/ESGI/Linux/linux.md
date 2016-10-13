---
layout: page
show_meta: false
title: "Linux"
header:
   image_fullwidth: "header_unsplash_5.jpg"
permalink: "/esgi/linux/"
breadcrumb: true
---

# **Cours**
<ul>
    {% for post in site.categories.cours_linux %}
    <li><a href="{{ site.url }}{{ post.url }}">{{ post.title }}</a></li>
    {% endfor %}
</ul>

# **Exercices**
<ul>
    {% for post in site.categories.exercice_linux %}
    <li><a href="{{ site.url }}{{ post.url }}">{{ post.title }}</a></li>
    {% endfor %}
</ul>
