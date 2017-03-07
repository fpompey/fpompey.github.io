---
layout: page
title:  "Cours Langage de scripting Shell et Python"
teaser: "Cours Langage de scripting Shell et Python lors de la semaine du 06 Mars 2017"
breadcrumb: false
tags:
    - esgi
    - langage_scripting_shell_python
    - cours
categories:
    - cours_langage_scripting_shell_python
show_meta: false
---

# Synopsis

Python est un logiciel OpenSource, dérivé du C et du Java en fin d'année 1980. Python est présent dans de nolbreux llogiciels tels que les annuairesLDAP, langage de prédilection pour XML, inclus dans Open Office...

Il gère par lui-même ses ressources, intègre un système d'exeption pour la gestion des erreurs. Les librairies permettent la manipulation dechaine de caractères, de services Unix/linux.

## Implémentations

  1. Cpython: écrite en C permettant des extensions de python.   
  Elle est disponible sur toutes les plateformes.

  2. Jython: écrite en Java permet l’utilisation des bibliothèques Java (Swing…), la JVM.

  3. Ironpython: écrite en C# pour la plateforme .Net

  4. PyPy: écrite en Python, niveau de services équivalent à Cpython.   
  (Projet de recherche européen d’un interpréteur Python en Python)

  5. StacklessPython: écrite pour la programmation parallèle.   
  Elle supprime la pile du langage C.

## Structure d'un programme Python

 - Une ligne se termine par un passage à la ligne
 - Une instruction par ligne (ou séparées par ‘‘;’’)
 - Pas plus d e 80 caractères ( / pour la continuité des lignes)
 - Indentation pour un bloc : 4 car actères (ou TAB).

*Exemple :*

**En langage C**

    int a=0;
    for(inti=0;i<10;i++)
    { a=a+1;
    } fin du bloc explicite

**En Python**

     a=o
     { for i in range(10) :
     a+=i
     // fin de bloc implicite

## Convention de nommage

 - Variables en minuscule, exemple : mon_id
 - Constante en majuscule, exemple : PI=3.14
 - Classe mixe des deux

*Exemple :*

    class MaClasse

  - Fonction mixe des deux

*Exemple :*

    defmaFonction()

## Les mots réservés

![Mots réservés](http://portfolio.fpompey.com/images/ESGI/Langage_de_scripting_Shell_Python/Mot_reserver.png)

## Opérateurs principaux

![Opérateurs principaux](http://portfolio.fpompey.com/images/ESGI/Langage_de_scripting_Shell_Python/Operateurs_principaux.png)

## Le type chaine

![Type Chaine](http://portfolio.fpompey.com/images/ESGI/Langage_de_scripting_Shell_Python/Type_Chaine.png)

**Attention, le caractère n'existe pas en Python**

Le triple double guillemets permet d’entrer une chaîne decaractères sur plusieurs lignes, y compris les caractères de retour de ligne.

## Les entrés / sorties

La saisie à l’écran se fait avec la fonction standard

    input()

Cette fonction effectue toujours une saisie en mode texte avec la possibilité de changer de type ensuite

    (transtypage)

La sortie s’effectue par la fonction

    print()

## Instructions

Une fonction peut être définie n’importe où dans le programme.

Une fonction renvoie toujours une valeur unique.   
Par défaut il s’agit de **None**.

Une fonction ou une classe peut être définie sans instructions (vide) avec le mot-clé **pass**

L’instruction **pass** ne fait rien :  
exemple attente d’une interruption…

*Exemple:*

    def ma_fonction():
      pass

    class ma_classe(object):
      pass

## Instructions conditionnelles :

L’instruction **not**: elle renverse une condition
L’instruction **if**

![Instructions Conditionnelles 1](http://portfolio.fpompey.com/images/ESGI/Langage_de_scripting_Shell_Python/Instructions_conditionnelles1.png)

Les instructions **else / elif**

![Instructions Conditionnelles 2](http://portfolio.fpompey.com/images/ESGI/Langage_de_scripting_Shell_Python/Instructions_conditionnelles2.png)

**Attention, le mot clé switch n’existe pas en Python**

## Les itérations

L'instruction **for**

![Itération 1](http://portfolio.fpompey.com/images/ESGI/Langage_de_scripting_Shell_Python/Iterations1.png)

L'instruction **while**

![Itération 2](http://portfolio.fpompey.com/images/ESGI/Langage_de_scripting_Shell_Python/Iterations2.png)

Instruction **break**: termine l’itération.

![Itération 3](http://portfolio.fpompey.com/images/ESGI/Langage_de_scripting_Shell_Python/Iterations3.png)

Instruction **return**: autre moyen de terminer l’itération.

![Itération 4](http://portfolio.fpompey.com/images/ESGI/Langage_de_scripting_Shell_Python/Iterations4.png)

L'instruction **continue**: permet de court-circuiter une boucle

![Itération 5](http://portfolio.fpompey.com/images/ESGI/Langage_de_scripting_Shell_Python/Iterations5.png)

Les intructions **eval et exec**: les deux mots permettent d'interpréter le contenu d'une chaine comme une instruction.

![Itération 6](http://portfolio.fpompey.com/images/ESGI/Langage_de_scripting_Shell_Python/Iterations6.png)

![Itération 7](http://portfolio.fpompey.com/images/ESGI/Langage_de_scripting_Shell_Python/Iterations7.png)

La différence entre **exec et eval** est que **eval** renvoie une valeur alors que **exec** exécute du code

## Techniques Fonctionnelles

Les fonctions Lambda:

 - Comme avec **def, lambda** désigne une expression qui renvoie un objet fonction.
 - **Lambda** est une exression et non une instruction
 - Une telle fonctione est **anonyme**
 - Un nom peux-être associé à une fonction **lambda**
 - Les fonctions **lambda** sont très pratiques pour créer des fonctions jetables
 - On ne peut les écrire que sur une ligne
 - On ne peux pas avoir plus d'une instruction dans la fonction

## Modules Python

Un module est un programme Python qui contient des fonction (méthodes) variées et prêtes à l'emploi.  
Un module est importé par le mot **import**

*Exemple:*

    os : pour communiquer avec le système
    sys : pour la gestion des entrées : sorties
    random : pour la générations des nombres aléatoires
    time : pour la gestion du temps
    calendaire : fonctions calendriers
    math : fonctions et constantes math
    Tkinter : interfaces graphiques
    urllib : pour récupérer des données d'internet avec Python

## Les Listes

 - Une liste est une struture de données très flexible, ordonnée et modifiable.
 - Elle peut contenir des valeurs de types différents.

*Quelques méthodes:*

    L.sort(): tri de la liste L
    L.append(val): ajout de val dans L
    L.reverse(): inverse L
    L.remove(val): supprime val de L
    L.pop(): supprime le dernier élément de L
    L.count(val): nomnre d'occurence de val dans L

![Liste 1](http://portfolio.fpompey.com/images/ESGI/Langage_de_scripting_Shell_Python/Liste1.png)

![Liste 2](http://portfolio.fpompey.com/images/ESGI/Langage_de_scripting_Shell_Python/Liste2.png)

**Résultat:**

![Liste 3](http://portfolio.fpompey.com/images/ESGI/Langage_de_scripting_Shell_Python/Liste3.png)
