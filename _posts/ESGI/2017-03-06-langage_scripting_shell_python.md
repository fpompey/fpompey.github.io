---
layout: page
title:  "Langage de scripting Shell et Python"
breadcrumb: true
tags:
    - langage_script_shell_python
categories:
    - esgi
show_meta: false
---

# Cours
<ul>
    {% for post in site.categories.cours_langage_script_shell_python %}
    <li><a href="{{ site.url }}{{ post.url }}">{{ post.title }}</a></li>
    {% endfor %}
</ul>

# Exercices
<ul>
    {% for post in site.categories.exercice_langage_script_shell_python %}
    <li><a href="{{ site.url }}{{ post.url }}">{{ post.title }}</a></li>
    {% endfor %}
</ul>
