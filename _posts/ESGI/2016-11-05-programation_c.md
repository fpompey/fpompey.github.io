---
layout: page
title:  "Programation C"
breadcrumb: true
tags:
    - programation_c
categories:
    - esgi
show_meta: false
---

# Cours
<ul>
    {% for post in site.categories.cours_programation_c %}
    <li><a href="{{ site.url }}{{ post.url }}">{{ post.title }}</a></li>
    {% endfor %}
</ul>

# Exercices
<ul>
    {% for post in site.categories.exercice_programation_c %}
    <li><a href="{{ site.url }}{{ post.url }}">{{ post.title }}</a></li>
    {% endfor %}
</ul>
