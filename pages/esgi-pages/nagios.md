---
layout: page
title:  "Nagios"
breadcrumb: true
header: no
permalink: "/esgi/nagios"
tags:
    - nagios
categories:
    - esgi
show_meta: false
---

# Cours
<ul>
    {% for post in site.categories.cours_nagios %}
    <li><a href="{{ site.url }}{{ post.url }}">{{ post.title }}</a></li>
    {% endfor %}
</ul>

# Exercices
<ul>
    {% for post in site.categories.exercice_nagios %}
    <li><a href="{{ site.url }}{{ post.url }}">{{ post.title }}</a></li>
    {% endfor %}
</ul>
