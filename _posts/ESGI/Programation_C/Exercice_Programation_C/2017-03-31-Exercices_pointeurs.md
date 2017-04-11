---
layout: page
title:  "Exercice Pointeurs"
teaser: "Exercice Pointeurs C lors de la semaine du 31 Mars 2017"
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

Pour cet exercice, nous allons utiliser les instructions suivantes pour initialisez les variables dont nous avons besoin :

    int tab[] = { 12 , 23 , 34 , 45 , 56 , 67 , 78 , 89 ,90 };
    int *p ;
    p = tab ;

    Quelles valeurs fournissent les expressions suivantes :

    a. *p
    b. *p+2
    c. *p-1
    d. *(p+2)
    e. *(p-1)
    f. (*(p+3)-*(p+1))+10
    g. *(p+*(p+8)-tab[7])

**Résultats:**

    int main()
    {
        int tab[]={12,23,34,45,56,67,78,89,90};
        int *p;
        p = tab;

        printf("%d", *p); //12
        printf("\n%d", *p+2); //14
        printf("\n%d", *p-1); //11
        printf("\n%d", *(p+2)); //34
        printf("\n%d", *(p-1)); //random
        printf("\n%d", (*(p+3)-*(p+1))+10); // 32
        printf("\n%d", *(p+*(p+8)-tab[7])); //23
    }

# Exercice 2:

Ecrire une fonction permettant de permuter deux variables reçues en paramètres.

**Résultats:**

    void mafonction(int *a, int *b)
    {
      int temp = *a;
      *a = *b;
      *b= temp;

      printf("%d", *a);
      printf("\n%d", *b);
    }

    int main()
    {
        int x=6, y = 10;

        mafonction(&x, &y);
    }

# Exercice 4:

Ecrire une fonction qui prend comme argument un tableau tab et sa taille t, et l’initialise de manière à ce que tab[t] = t .  
Utilisez cette fonction pour initialiser un tableau puis affichez les valeurs stockées pour vérifier que l’initialisation est correcte.

**Resultats:**

    void mafonction(int *tab, int taille)
    {
        int i=0;

        for (i = 0 ; i < taille ; i++)
            *(tab + i)= taille;
    }

    int main()
    {
        int tab[9];
        int t = sizeof(tab)/ sizeof(*(tab));

        mafonction(tab,t);
    }

# Exercice 5:

    Sur le même principe que pour la question 4), écrivez une fonction qui prend comme
    argument un tableau et sa taille, le modifie en multipliant les valeurs stockées par la taille t
    du tableau, et retourne le plus grand élément. Testez cette fonction


**Resultats:**

    int modifier(int *tab, int taille)
    {
      int cpt=0, max = tab[0];
      for(cpt=0;cpt<taille;cpt++)
      {
        *(tab+cpt)=*(tab+cpt) * taille;
        if (*(tab+cpt) > max)
        {
          max = *(tab+cpt);
        }
      }
      return max;
    }

    int main
    {
      int tab[]={7,8,9,10};
      int valeur max;
      valeur_max = modifier (tab, sizeof(tab)/sizeof(int));
      printf("MAX: %d", valeur_max);
    }
