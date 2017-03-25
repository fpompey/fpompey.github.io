---
layout: page
title:  "Urbanisation DataCenter"
breadcrumb: true
tags:
    - urbanisation_dc
categories:
    - esgi
show_meta: false
---

# Cours
<ul>
    {% for post in site.categories.cours_urbanisation_dc %}
    <li><a href="{{ site.url }}{{ post.url }}">{{ post.title }}</a></li>
    {% endfor %}
</ul>

# Exercices
<ul>
    {% for post in site.categories.exercice_urbanisation_dc %}
    <li><a href="{{ site.url }}{{ post.url }}">{{ post.title }}</a></li>
    {% endfor %}
</ul>
