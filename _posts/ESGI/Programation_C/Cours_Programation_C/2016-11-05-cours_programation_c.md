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

1) On appelle palindrome une suite de caractères qui se lit de la même façon dans les deux
sens. Ecrire une fonction pour déterminer si un mot (représenté par un tableau de
caractères) est un palindrome.

    #include <stdio.h>
    #include <stdlib.h>

    int main()
    {
    char mot[100];
    printf ("Tapez un mot: ");
    scanf ("%s",&mot);

    if(palindrome(mot)==1)
    {
        printf("C'est un palindrome");
    }

    else
    {
        printf("Ce n'est pas un palindrome");
    }
    return 0;
    }

    int palindrome(char *mot)
    {
    int taille = strlen(mot);
    int cpt;

    for (cpt=0; cpt<taille/2; cpt++)
    {
    if(mot[cpt]!= mot[taille-cpt-1])
    {
     return 0;
    }
    }
    return 1;
    }

2) Ecrire un programme qui lit une saisie d’une chaine de caractères puis affiche sa longueur
(sans utiliser strlen()).

3) Ecrire un programme qui demande la saisie de deux chaines de caractères et qui en créée
une troisième en concaténant les deux chaines lues.

4) Ecrire un programme qui demande la saisie de deux chaines de caractères et qui les
compares pour indiquer si les deux chaines sont identiques ou pas.

5) Ecrire un programme qui demande la saisie de deux chaines de caractères et d’un nombre
entier. Le programme devra ensuite comparer les n (le nombre entier saisi) premiers
caractères de chacune des chaines.

6) Ecrire un programme qui demande la saisie de deux chaines de caractères et qui recherche la
deuxième chaine dans la première. Le résultat attendu est du type oui/non

7) Ecrire un programme qui demande la saisie d’une chaine de caractères et qui l’affiche en
majuscules. Pour y parvenir, vous devrez manipuler les valeurs ASCII des caractères (voir
table ASCII)

8) Même question que pour la 7 mais en minuscule

9) Ecrire un programme qui lit un verbe régulier en « er » au clavier et qui en affiche la
conjugaison au présent de l’indicatif. Contrôlez s’il s’agit bien d’un verbe en « er » avant de le
conjuguer. Vous pouvez utiliser les fonctions de string.h