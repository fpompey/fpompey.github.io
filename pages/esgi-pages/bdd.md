---
layout: page
title:  "Base de données relationnelles"
breadcrumb: true
header: no
permalink: "/esgi/bdd"
tags:
    - bdd
categories:
    - esgi
show_meta: false
---

# Cours
<ul>
    {% for post in site.categories.cours_bdd %}
    <li><a href="{{ site.url }}{{ post.url }}">{{ post.title }}</a></li>
    {% endfor %}
</ul>

# Exercices
<ul>
    {% for post in site.categories.exercice_bdd %}
    <li><a href="{{ site.url }}{{ post.url }}">{{ post.title }}</a></li>
    {% endfor %}
</ul>
