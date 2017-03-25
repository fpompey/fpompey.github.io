---
layout: page
title:  "Panorama du Cloud Computing"
breadcrumb: true
tags:
    - cloud_computing
categories:
    - esgi
show_meta: false
---

# Cours
<ul>
    {% for post in site.categories.cours_cloud_computing %}
    <li><a href="{{ site.url }}{{ post.url }}">{{ post.title }}</a></li>
    {% endfor %}
</ul>

# Exercices
<ul>
    {% for post in site.categories.exercice_cloud_computing %}
    <li><a href="{{ site.url }}{{ post.url }}">{{ post.title }}</a></li>
    {% endfor %}
</ul>
