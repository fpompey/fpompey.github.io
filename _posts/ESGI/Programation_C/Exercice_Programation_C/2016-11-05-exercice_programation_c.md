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

**Exercice9:**

Pour les questions suivantes, inscrivez les instructions nécessaires directement dans le
main().
a) Donnez les instructions pour calculer l'aire et le périmètre d'un cercle
b) Donnez les instructions pour calculer la longueur de l'hypoténuse dans un triangle
rectangle (utilisez le théorème de Pythagore)
Utilisez la librairie standard math.h pour manipuler PI et calculer les puissances (ainsi
que les racines)
