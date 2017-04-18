---
layout: page
title:  "Linux"
breadcrumb: true
header: no
permalink: "/esgi/linux"
tags:
    - linux
categories:
    - esgi
show_meta: false
---

# Cours
<ul>
    {% for post in site.categories.cours_linux %}
    <li><a href="{{ site.url }}{{ post.url }}">{{ post.title }}</a></li>
    {% endfor %}
</ul>

# Exercices
<ul>
    {% for post in site.categories.exercice_linux %}
    <li><a href="{{ site.url }}{{ post.url }}">{{ post.title }}</a></li>
    {% endfor %}
</ul>
