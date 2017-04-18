---
layout: page
title:  "Projets"
breadcrumb: true
header: no
permalink: "/esgi/projets"
tags:
    - projet
categories:
    - esgi
show_meta: false
---

# Projet
<ul>
    {% for post in site.categories.projet %}
    <li><a href="{{ site.url }}{{ post.url }}">{{ post.title }}</a></li>
    {% endfor %}
</ul>
