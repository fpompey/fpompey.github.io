---
layout: page
title:  "Architecture et Réseaux"
breadcrumb: true
tags:
    - architecture_reseaux
categories:
    - esgi
show_meta: false
---

# Cours coucou
<ul>
    {% for post in site.categories.cours_architecture_reseaux %}
    <li><a href="{{ site.url }}{{ post.url }}">{{ post.title }}</a></li>
    {% endfor %}
</ul>

# Exercices
<ul>
    {% for post in site.categories.exercice_architecture_reseaux %}
    <li><a href="{{ site.url }}{{ post.url }}">{{ post.title }}</a></li>
    {% endfor %}
</ul>
