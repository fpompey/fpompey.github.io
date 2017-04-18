---
layout: page
show_meta: false
title:  "Algorithme Avancée"
breadcrumb: true
header: no
permalink: "/esgi/algorithme_avancee"
tags:
    - algorithme
categories:
    - esgi
---

# Cours
<ul>
    {% for post in site.categories.cours_algorithme_avancee %}
    <li><a href="{{ site.url }}{{ post.url }}">{{ post.title }}</a></li>
    {% endfor %}
</ul>

# Exercices
<ul>
    {% for post in site.categories.exercice_algorithme_avancee %}
    <li><a href="{{ site.url }}{{ post.url }}">{{ post.title }}</a></li>
    {% endfor %}
</ul>
