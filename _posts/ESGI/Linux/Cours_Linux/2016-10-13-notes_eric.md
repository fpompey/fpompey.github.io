---
layout: page
title:  "Notes Eric"
teaser: "Notes Eric lors de la semaine du 10 Octobre 2016"
breadcrumb: false
tags:
    - ESGI
    - Linux
    - Cours
categories:
    - cours_linux
show_meta: false
---


Gestion des droits sur un fichier  
on peut les gérer pour un utilisateur, pour un groupe et pour les autres  
les droits sont:  
Lecture (4)  
Ecriture (2)  
Execution (1)  
La somme nous donne l'ensemble des droits (par exemple 7 correspond à l'ensemble des droits)  

Pour créer des utilisateurs et des groupes:  
passer en root (su puis le login) et utiliser les commandes suivantes:  

adduser (ajout utilisateur)  
deluser (suppression utilisateur)  
usermod (droits de l'utilisateur)  
addgroup (creation du groupe)  
delgroup (suppression du groupe)  

options du usermod:
-d rep déplace le home
-g  modifie le groupe initial
-G ajoute à plusieurs groupes
-s ajouter au shell

les droits par défaut lors de la création d'un fichier sont de 666
mais il existe le umask (user mask) qui vaut 022 et change la valeur des droits:
 666
-022
 644

Donc lors de la création d'un fichier, par défaut on aura 644
pour les répertoires les droits par défaut son 777 donc 755 après le umask.
