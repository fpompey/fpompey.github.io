---
layout: page
title:  "Windows"
breadcrumb: true
header: no
permalink: "/esgi/windows"
tags:
    - windows
categories:
    - esgi
show_meta: false
---

# Cours
<ul>
    {% for post in site.categories.cours_windows %}
    <li><a href="{{ site.url }}{{ post.url }}">{{ post.title }}</a></li>
    {% endfor %}
</ul>

# Exercices
<ul>
    {% for post in site.categories.exercice_windows %}
    <li><a href="{{ site.url }}{{ post.url }}">{{ post.title }}</a></li>
    {% endfor %}
</ul>
