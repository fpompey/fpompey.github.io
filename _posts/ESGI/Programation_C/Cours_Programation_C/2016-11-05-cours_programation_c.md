---
layout: page
title:  "Cours Programation C"
teaser: "Cours Programation C lors de la semaine du 31 Octobre 2016"
breadcrumb: false
tags:
    - ESGI
    - programation_c
    - Cours
categories:
    - cours_programation_c
show_meta: false
---

# Initiation

La directive *#include* permet de dire que l'on va utiliser une librairie.  
En utilisant les librairies inclues dans le compileur, on l'écrit *#include<librairie.h>*  
En utilisant une librairie qu'on a téléchargée sur internet, on l'écrit *#include"chemin_d'accès.h"*  
Le chemin peut être relatif.  


La fonction main:
  - elle est obligatoire  
  - c'est le point d'entrée lors de l'execution  
  - elle est unique pour tout le programme  
  - une fois toutes les instructions du main executées, le programme s'arrête et retourne une valeur

La valeur retournée sera soit 0 (tout s'est executé correctement) soit une valeur différente de 0 (plantage)  

Le return permet de terminer une fonction et de renvoyer une valeur  

Le printf écrit des données sur la sortie standard, le **\n** permet le retour à la ligne  

Noms de variables:  
  - sensibles à la casse
  - mot explicite
  - pas d'espace
  - a-z, A-Z, 0-9, _
  - ne doit jamais commencer par un chiffre
  - pas de mot clé de langage

**nombre entier: int**
    %d

**nombre réel: float**
    %f  

**caractères: char**  
    %c
