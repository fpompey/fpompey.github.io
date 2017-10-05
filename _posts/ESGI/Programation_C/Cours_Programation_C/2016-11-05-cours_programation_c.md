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
conjuguer. Vous pouvez utiliser les fonctions de string.


## Structures

Une structure est une assemblage de variables qui peuvent être de différents types (à la différence des tableaux où tous les éléments sont de même type).

**Définition:**

Les structures se définissent soit **avant le main** soit dans le **fichier d'en-tête**(fichier.h)

    struct NomDeMaStructure
    {
      int variable1;
      double variable2;
      char variable3;
    };

**Attention, le nom de la structure doit toujours commencer par une majuscule.**  
**Avoir un ; à la fin du block stucture**

    struct Point
    {
      int x;
      int y;
    };

    int main()
    {
      *struct Point* pointA; // point A est une variable de type struct de point.
    }

Pour éviter l'utilisation du mot-clé *struct* lors de la définition de variables du type de la structure, on utilise le mot-clé **typedef**  
Il s'écrit juste après la structure.   
**typedef** (*nom à remplacer*) puis (*nouveau nom*) ;

**Exemple:**

    typedef struct Point Point;

**Autre Exemple:**

    int main()
    {
      Point Point B;
      pointB.x = 17;
      pointB.y = 6;
    }

On utilise l'opérateur **.** pour accéder aux variables d'une structure lorsque l'on est sur une variable de type de cette même structure.

**Initialisation:**

Point pointB = {0 , 0}; // **valeur dans l'ordre de définition des variables dans la structure, attention il doit y en avoir le même nombre**

*Est équivalent*

pointB.x=0;
pointB.y=0;

###  Pointeur de Structures

Un pointeur de structure est une variable contenant l'adresse mémoire d'une structure.

Point* ppoint = NULL;

**Exemple:**

Pour transmettre une structureà une fonction, on enverra l'adresse mémoire de cette structure.

    void multiplier(Point *ppoint, int nombre)
    {
      (*ppoint).x = (*ppoint).x * nombre;

      ou est équivalent

      ppoint -> x = (ppoint -> x) * nombre; // **L'opérateur "->" n'existe que dans le cas d'un pointeur de structure.**
    }

    int main()
    {
      Point pointA;
      pointA.x=7;
      pointA.y=8;
      multiplier(&pointA, 6);
      printf("%d %d", pointA.x, pointA.y);

      return 0;
    }

### Enumérations

C'est un ensemble de valeurs.

**Exemple:**

    enum Volume
    {
      FAIBLE, MOYEN, FORT
    };
    typedef enum Volume Volume;

    int main()
    {
      Volume son = Volume FAIBLE;

      if(son == Volume.FORT)
      {
        son = Volume.MOYEN;
      }
    }

### Fichiers

- En C la manipulation d'un fichier s'effectue à l'aide d'un pointeur sur une structure de type FILE
- La variable contient l'adresse mémoire du début d fichier (le pointeur sur FILE)

**1/ Ouverture de fichier**

fopen(); fonction permettant d'ouvrir un fichier
-> elle retourne un pointeur sur le fichier ouvert (FILE*)
-> elle prend 2 paramètres :
  - Le nom du fichier -> "toto.txt"
                      -> "C:\\files\\toto.txt"  Il faut doubles les antislashs pour échapper le caractère
  - Mode d'ouverture (pour le traitement qui va suivre)

**Modes d'ouverture**

**"r"** (read) : ouvre le fichier en lecture (uniquement si il existe déjà)
**"w"** (write) : ouvre le fichier en écriture. Si inexistant, le fichier est créé, si il existe déjà, son contenu est écrasé
**"a"** (append) : ouvre le fichier en écriture (comme le "w") mais il ajoute le contenu à la fin si le fichier existe déjà
**"r+"** : Lecture/écriture uniquement si le fichier existe déjà (il ne permet pas de le créer)
**"w+"** : Lecture/écriture, créé le fichier si inexistant et l'écrase si existant
**"a+"** : Lecture/écriture, créé le fichier si inexistant, et ajoute à la suite si existant

*Exemple :*

    FILE* fichier= fopen(**"monfichier.txt"** *(Nom ou chemin du fichier)*, **"w"** *(Mode d'ouverture 1 seul parmi la liste)*);

    if(fichier !=NULL){
      Le fichier est bie ouvert
    }

    else{
      printf("Echec d'ouverture du fichier");
    }

**2/ Fermeture d'un fichier**

Quelque soit son mode d'ouverture, chaque fichier ouvert doit être fermé

    fclose(*(pointeur sur fichier)*);

**3/ Ecrire des données dans un fichier**

    fputc => écrit un seul caractère à la fois
    fputs => écrit une chaîne de caractères
    fprintf => écrit chaine formatée

*Exemple:*

    FILE * fichier= fopen ("file.txt", "w");
    if(ficher!=NULL){
      fputc(**'B'** *(caractère à écrire)*, **fichier** *(pointeur sur fichier ouvert en écriture)*);
      fputs(**"Bonjour"** *(chaine de caractères)*, **fichier**);
      int jour = 22;
      fprintf("Lundi **%d** *(jour)* mai", fichier);
      fclose(fichier);

    }

**4/ Lecture de fichier**

fgetc(*(pointeur sur fichier)*) => Permet de lire un caractère à la fois dans le fichier

-> La fonction retourne le caractère lu
-> Elle retourne EOF (end of file) lorsqu'elle arrive à la fin du fichier:

    FILE * fic = fopen ("fichier.txt", "n");
    if(fic!=NULL)
    {
      do
      {
        char carac = fgetc(fic);
        printf("%c", carac);
      }
      while(carac!=EOF);
      fclose(fic);
    }

**5/ Curseur**

ftell() => donne la position du curseur
fseek() => permet de déplacer le curseur
rewind() => permet de remettre la position du curseur au début du fichier
