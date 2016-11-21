---
layout: page
title:  "Exercice Programation C"
teaser: "Exercice Programation C lors de la semaine du 31 Octobre 2016"
breadcrumb: false
tags:
    - ESGI
    - programation_c
    - Exercice
categories:
    - exercice_programation_c
show_meta: false
---

# Comprendre le fonctionnement

**Exercice 1:**

char c = 'a';
printf( " %c \n " , c);
printf( " %c \n " , c++);
printf( " %c \n " , c + 1);

    1. Définis la variable c puis prend la valeur a
    2. Afficher un espace la variable c suivi d'un retour a la ligne, il fera un espace supplémentaire sur la ligne suivante = " a "
    3. Afficher un espace la variable c = a suivi d'un retour a la ligne, il fera un espace supplémentaire sur la ligne suivante **(a la fin de la ligne le caractère c est incrémenté et passe à b)** = "  a "
    4. Afficher un espace la variable c + 1 = c suivi d'un retour a la ligne, il fera un espace supplémentaire sur la ligne suivante **(la variable c qui était b est incrémenté de 1 et devient c)** = "  c "

**Exercice 2:**

int i;
printf(" %d \n " , i );
printf(" %d \n " , i + 1 );
i=6;
printf(" %d \n " , i - 1 );

    1. Définis la variable i
    2. Afficher un espace puis le nombre i (celui n'as pas été défini auparavant) suivi d'un espace puis un retour à la ligne, il fera un espace supplémentaire sur la ligne suivante = " ? "
    3. Afficher un espace puis le nombre i + 1 (celui n'as pas été défini auparavant) suivi d'un espace puis un retour à la ligne, il fera un espace supplémentaire sur la ligne suivante = "  ? "
    4. i prend la valeur 6
    5. Afficher un espace puis le nombre i=6 - 1 soit 5 suivi d'un espace puis un retour à la ligne, il fera un espace supplémentaire sur la ligne suivante = "  5 "

**Exercice 3:**

int a = 4 , b = 5 , c = 6;
c = a / b - 2;
printf(" %d \n", c);
c = c % a;
printf(" %d \n", c);

    1. Définis la variable a qui prend la valeur 4, définis la variable b qui prend la valeur 5, définis la variable x qui prend la valeur 6
    2. Effectue le calcul c = 4 / 5 -2 donc c prend la valeur -2
    3. Affiche un espace la variable c qui est devenue 0 puis un retour a la ligne, il fera un espace supplémentaire sur la ligne suivante = " -2 "
    4. Effectue le calcul c = 0 % 4 donc c prend la valeur -2
    5. Affiche un espace la variable c qui est devenue 0 puis un retour a la ligne, il fera un espace supplémentaire sur la ligne suivante = " -2 "

**Exercice 4:**

int a = 2, b = 4, c = 2;
int d = a / b / c;
printf(" %d \n" , d);
d = b / b / c;
printf(" %d \n" , d);

    1. Définis la variable a qui prend la valeur 2, définis la variable b qui prend la valeur 4, définis la variable x qui prend la valeur 2
    2. Définis la variable d puis prend la valeur de l'opération 2 / 4 / 2 = 0
    3. Affiche un espace la variable d qui est devenue 0 puis un retour a la ligne, il fera un espace supplémentaire sur la ligne suivante = " 0 "
    4. d prend la valeur de l'opération 4 / 4 / 2 = 0
    5. Affiche un espace la variable d qui est devenue 0 puis un retour a la ligne, il fera un espace supplémentaire sur la ligne suivante = " 0 "

**Exercice 5:**

int a = 3, b = 4;
resultat = (a + b) % b;
printf(" %d ",resultat);

    1. Définis la variable a qui prend la valeur 3, définis la variable b qui prend la valeur 4
    2. Resultat prend la valeur de l'opération (3 + 4) % 4 = 3 *(Mais la variable resultat n'étant pas déclaré le programme va planter)*
    3. Affiche un espace la variable resultat qui est devenue 3 puis un espace supplémentaire = " 3 " *(Mais la variable resultat n'étant pas déclaré le programme va planter)*

**Exercice 6:**

int a = 45, b = 10, 4c = 2;
printf(" %d \n ", a);
printf(" %d ", a / b);

    1. Définis la variable a qui prend la valeur 45, définis la variable b qui prend la valeur 10, 4c qui prend la valeur 2 *(ce qui risque de provoquer une erreur car la variable commence par un chiffre)*
    2. Affiche un espace la variable a qui est 45 puis un retour a la ligne, il fera un espace supplémentaire sur la ligne suivante = " 45 "
    3. Affiche un espace la variable 45 / 10 qui est 4 puis un espace supplémentaire = "  4 "

**Exercice 7:**

int a = 3, b = 7;
printf(" %d ", a + b / b * b )

    1. Définis la variable a qui prend la valeur 3, définis la variable b qui prend la valeur 7
    2. Affiche un espace la variable 3 + 7 / 7 * 7 = 10  qui est 10 puis un espace supplémentaire = " 10 " *(Le programme va planter car il manque un ; sur le seconde ligne)*

**Exercice 8:**

En utilisant uniquement les fonctions d’entrée-sortie standard scanf() et printf(), vous
devrez mettre en place les instructions au sein de votre main() permettant de réaliser le
traitement suivant :
> Introduire la date du jour (jour mois année) : 11 10 2016
> jour : 11
mois : 10
année : 2016

    int jour=0, mois=0, annee=0;
    printf("Saisir date:\n"),
    scanf("%d", &jour);
    scanf("%d", &mois);
    scanf("%d", &annee);
    printf("jour %d\n mois %d\n annee %d\n", jour, mois, annee);


**Exercice9:**

Pour les questions suivantes, inscrivez les instructions nécessaires directement dans le
main().
a) Donnez les instructions pour calculer l'aire et le périmètre d'un cercle
b) Donnez les instructions pour calculer la longueur de l'hypoténuse dans un triangle
rectangle (utilisez le théorème de Pythagore)
Utilisez la librairie standard math.h pour manipuler PI et calculer les puissances (ainsi
que les racines)

    # include <math.h>
    float aire, rayon = 8.3, perimetre,
    aire = M PI * pow (rayon 2);
    perimetre = 2 * M PI * rayon;
    resultat = sqrt(pow (coteA, 2) + pow (coteB, 2));

# Boucle et conditions

1) Ces deux boucles for comprennent-elles le même nombre d’itérations ?
  for (j=0 ; j<8 ; j++)
  for(j=0 ; j<=8 ; j++)

    1. Non la deuxième fera une itération en plus car est compris dans la boucle contrairement à la première.

2) La boucle for ci-après :
  for( j = 65 ; j < 72 ; j++ )
    printf("%c", j) ;

Est-elle équivalente à cette boucle while ?

  int k = 65;
  while( k < 72 )
  {
    printf( "%c" , k );
    k++;
  }

    1. Oui, l'itération pour le for se fait avant de rentrer dans la boucle, alors que le while l'itération se fera en sortie de boucle, il effectuera donc le même nombre d'itération.

3) Remplacez la boucle suivante par une boucle for :
  int k=100 ;
  do
  {
    printf("%c", k) ;
    k++ ;
  }

  while(k < 100);

    1. for(int j = 100, j < 100, j++)
        printf("%c" , j);

4) Ecrire un programme qui calcule la somme des nombres entiers de 1 à 100

    1.
    #include <stdio.h>
    #include <stdlib.h>

    int main()
    {
        # include <math.h>
        int i, somme = 0;
        for(i = 0 ; i <= 100 ; i++)
          somme = somme +i;
          printf("La somme des nombres entiers de 1 a 100 est %i", somme);
    }


5) Ecrire un programme qui calcule la somme des nombres entiers dans un intervalle donné.

  Demandez à l’utilisateur la saisie des deux bornes de l’intervalle
  Pensez à vérifier la cohérence des données saisies


  1.
  #include <stdio.h>
  #include <stdlib.h>

  int main()
  {
      # include <math.h>
      int start, end, somme, pivot = 0;
      printf("Saisir le premier nombre\n");
      scanf("%d", &start);
      printf("Saisir le second nombre\n");
      scanf("%d", &end);

      if(end < start)
      {
        pivot = end;
        end = start;
        start = pivot;
      }

      for( ; start <= end ; start ++)
      somme += start;

      printf("La somme est egal a %d", somme);
  }

6) Ecrire un programme qui calcule la somme des nombres pairs de 1 à 100

    1.
    #include <stdio.h>
    #include <stdlib.h>

    int main()
    {
      # include <math.h>
      int i, somme = 0;
      for(i = 0 ; i <= 100 ; i++)
      {
          if (i%2 == 0)
          {
              somme = somme +i;
          }
      }  
      printf("La somme des nombres pairs de 1 a 100 est %i", somme);
    }

7) Ecrire un programme qui affiche les nombres de 1 à 20 par lignes de 3 nombres.

  Résultat attendu :
  1 2 3
  4 5 6
  7 8 …

    #include <stdio.h>
    #include <stdlib.h>

      int main()
      {
        int i;
        for(i = 1 ; i <= 20 ; i++)
        {
           if(i%3 == 0)
              printf("%d \n", i);
           else
              printf("%d ", i);
        }
      }

8) Ecrire un programme qui calcule la factorielle d’un nombre
  Rappels :
  Factorielle de 4 = 4x3x2x1 = 24
  Factorielle de 0 = 1

9) Même exercice que la question précédente mais à l’aide d’une fonction récursive
  Rappel : Une fonction récursive est une fonction qui s’appelle elle-même, en ayant
une condition de sortie (pour éviter les boucles infinies)

C - Boucles et conditions 2

10) Ecrire un programme qui permet la saisie d’un nombre entier et l’affiche à l’envers. Par
exemple, si l’utilisateur saisit 123456 le programme devra afficher 654321
  Rappel : 153 % 10 = 3 et 153 / 10 = 15

11) « Devine le nombre » :
Ecrire un programme sous la forme d’un jeu, un nombre est déterminé aléatoirement, tant
que l’utilisateur ne trouve pas le nombre en question par des saisies successives, il lui est
offert la possibilité d’effectuer une nouvelle tentative jusqu’à obtention du résultat.

  Affinez votre message en indiquant si le nombre recheché est plus grand ou
plus petit que le nombre saisi

  Ajoutez un nombre de tentatives maximum, provoquant ainsi une fin de
partie si ce nombre est atteint

12) « Multiples »
Ecrire un programme qui permet de savoir quels sont les multiples d’un nombre. On se
contentera de déterminer si le nombre est multiple de 2, 3, 7, 11.

Il est conseillé de créer une fonction pour chaque multiple, et d’effectuer ensuite votre
traitement en fonction du retour de ces différentes fonctions.
