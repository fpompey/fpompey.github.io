---
layout: page
title:  "Exercice Structures"
teaser: "Exercice Structures C lors de la semaine du 10 Avril 2017"
breadcrumb: false
tags:
    - ESGI
    - programation_c
    - Exercice
categories:
    - exercice_programation_c
show_meta: false
---

# Exercice 1:

Qu’affiche le programme suivant ? Si besoin, corrigez les erreurs de syntaxe

    # include <stdio.h>
    # include <string.h>

    typedef union
    {
      int i;
      float f;
      char str[20];
    } t_data;

    int main()
    {
      t_data data;

      data.i=10;
      data.f=220,5;
      strcpy(data.str, "Mobylette");

      printf("data.i : %d\n", data.i);
      printf("data.f : %f\n", data.f);
      printf("data.str : %s\n", data.str);

      return 0;

    }

**Résultats:**

    

# Exercice 2:

Définir une structure de données Heure permettant de représenter une heure au format
hh/mm/ss, puis écrire les fonctions suivantes :

  1. Conversion d’un élément de type Heure en un nombre de secondes (nombre entier)
  2. Conversion d’un nombre de secondes (nombre entier) en un élément de type Heure
  3. Addition de deux éléments de type Heure pour en former un troisième

# Exercice 3:

Voici des structures écrites en C pour manipuler des figures géométriques :
Un carré se manipule par les coordonnées x, y du coin haut-gauche et par la valeur de son
côté. Un rectangle par x,, y , sa longueur et sa largeur.
Mettre en œuvre les fonctions suivantes :

  1. Void carre_creer(t_carre *self, int x, int y, int longueur_cote)
  Permet d’initialiser un carré
  2. Void carre_detruire(t_carre *self)
  Permet de détruire un carré
  3.Void carre_afficher (t_carre *self)
  Permet d’afficher un carré : on affichera les coordonnées de ses quatre coins
  4. Void rectange_afficher(t_rectangle *self)
  Permet d’afficher un rectangle : on affichera les coordonnées de ses quatre coins
  5. Void carre_aire (t_carre *self)
  Permet d’afficher l’aire d’un carré
  6. Void rectangle_aire (t_carre *self)
  Permet d’afficher l’aire d’un rectangle
