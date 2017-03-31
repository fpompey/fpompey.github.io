---
layout: page
title:  "Algorithme Avancée"
breadcrumb: true
tags:
    - algorithme
categories:
    - esgi
show_meta: false
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
