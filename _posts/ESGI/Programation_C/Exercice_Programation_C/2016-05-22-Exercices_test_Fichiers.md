---
layout: page
title:  "Exercice Programation C"
teaser: "Exercice Programation C lors de la semaine du 22 Mai 2017"
breadcrumb: false
tags:
    - ESGI
    - programation_c
    - Exercice
categories:
    - exercice_programation_c
show_meta: false
---

# Exercice 1 :

    #include <stdio.h>
    #include <stdlib.h>

    int main()
    {
        FILE*f =fopen("fichier.txt", "w");
        if(f!=NULL){
            fputs("Hello World", f);
        }
        else{
            printf("Echec d'ouverture");
        }
    }
