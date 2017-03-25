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

<!-- TOC depthFrom:1 depthTo:6 withLinks:1 updateOnSave:1 orderedList:0 -->

- [Synopsis](#synopsis)
	- [Implémentations](#implmentations)
	- [Structure d'un programme Python](#structure-dun-programme-python)
	- [Convention de nommage](#convention-de-nommage)
	- [Les mots réservés](#les-mots-rservs)
	- [Opérateurs principaux](#oprateurs-principaux)
	- [Le type chaine](#le-type-chaine)
	- [Les entrés / sorties](#les-entrs-sorties)
	- [Instructions](#instructions)
	- [Instructions conditionnelles :](#instructions-conditionnelles-)
	- [Les itérations](#les-itrations)
	- [Techniques Fonctionnelles](#techniques-fonctionnelles)
	- [Modules Python](#modules-python)
	- [Les Listes](#les-listes)
	- [Les n-uplets (tuple)](#les-n-uplets-tuple)
	- [Les tableaux](#les-tableaux)
	- [Les ensembles (set)](#les-ensembles-set)
	- [Les dictionnaires (dict)](#les-dictionnaires-dict)
	- [Les fichiers](#les-fichiers)

<!-- /TOC -->

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

## Les n-uplets (tuple)

 - Un **n-uplet** est une structure de données très flexible, ordonnée et non modifiable.
  - Elle peux contenir des valeurs de types différents.

![N-Uplet 1](http://portfolio.fpompey.com/images/ESGI/Langage_de_scripting_Shell_Python/N-Uplet1.png)

![N-Uplet 2](http://portfolio.fpompey.com/images/ESGI/Langage_de_scripting_Shell_Python/N-Uplet2.png)

![N-Uplet 3](http://portfolio.fpompey.com/images/ESGI/Langage_de_scripting_Shell_Python/N-Uplet3.png)

![N-Uplet 4](http://portfolio.fpompey.com/images/ESGI/Langage_de_scripting_Shell_Python/N-Uplet4.png)

![N-Uplet 5](http://portfolio.fpompey.com/images/ESGI/Langage_de_scripting_Shell_Python/N-Uplet5.png)

## Les tableaux

 - Le tableau associatif est un type de données permettant de stocker des couples *(clé:valeur)* dont l'accès se fait par la **clé**.
  - La clé n'apparait qu'une fois dans le tableau.
  - La clé peux être définie par l'opérateur **in**
  - Le nombre de couples est calculé par la fonction **len()**

## Les ensembles (set)

 - Un sensemble est une collection non ordonnée d'éléments.
 - Les opérations sur les ensembles sont : **l'intersection, l'union, la différence**

![Ensemble 1](http://portfolio.fpompey.com/images/ESGI/Langage_de_scripting_Shell_Python/Ensemble1.png)

## Les dictionnaires (dict)

 - Un dictionnaire est une collection de couples **(clé:valeur)** qui n'occupent pas un ordre immuable.
 - Comme les listes lesdictionnaires sont modifiables.
 - Une clé peux être alphabétique,numérique ou tout type hashable ou table de hachage.

![Dictionnaire 1](http://portfolio.fpompey.com/images/ESGI/Langage_de_scripting_Shell_Python/Dictionnaire1.png)

![Dictionnaire 2](http://portfolio.fpompey.com/images/ESGI/Langage_de_scripting_Shell_Python/Dictionnaire2.png)

![Dictionnaire 3](http://portfolio.fpompey.com/images/ESGI/Langage_de_scripting_Shell_Python/Dictionnaire3.png)

![Dictionnaire 4](http://portfolio.fpompey.com/images/ESGI/Langage_de_scripting_Shell_Python/Dictionnaire4.png)

## Les fichiers

 - Un module ou librairie Python est un fichier contenant des définitions et des instructions Python.
 - Un paquetage est une collection de modules.
 - Il est possible d’importer des fichiers (.py ou .pyc) comme des modules ou une hiérarchie de modules complexes.
 - Un module est un bloc , il possède son espace de nommage.
 - Il peut contenir des variables, des fonctions, des classes et d’autres modules

**Exemple d'importation :**

    import monmodule
    from monmodule import mafonction

Autotest:

![Autotest](http://portfolio.fpompey.com/images/ESGI/Langage_de_scripting_Shell_Python/Autotest.png)

Importation:

![Importation](http://portfolio.fpompey.com/images/ESGI/Langage_de_scripting_Shell_Python/Importation.png)

Ouverture d'un fichier

![Ouverture](http://portfolio.fpompey.com/images/ESGI/Langage_de_scripting_Shell_Python/Ouverture.png)

 - Le fichier texte **fich.txt** est ouvert en lecture par défaut.
 - La primitive **type()** précise que **f** est un objet structure d’entrée /sortie.
 - La méthode **mro()** (Method Resolution Order) permet d’obtenir l’ordre dans lequel les méthodes et attributs sont recherchés dans les déclarations de classes (héritage)
 - La méthode **dir()** liste les méthodes et les attributs que l’objet **f** intègre.
 - La méthode **open** (nom du fichier, mode d’ouverture) renvoie un objet : descripteur de fichier **f**
 - Le mode d’ouverture précise les opérations à effectuer sur le fichier :

![Ouverture 2](http://portfolio.fpompey.com/images/ESGI/Langage_de_scripting_Shell_Python/Ouverture2.png)

Méthode de lecture:

![Lecture](http://portfolio.fpompey.com/images/ESGI/Langage_de_scripting_Shell_Python/Lecture.png)

Ecrire dans un fichier:

![Ecriture](http://portfolio.fpompey.com/images/ESGI/Langage_de_scripting_Shell_Python/Ecriture.png)

Se déplacer:

![Deplacer](http://portfolio.fpompey.com/images/ESGI/Langage_de_scripting_Shell_Python/Deplacer.png)

![Deplacer 2](http://portfolio.fpompey.com/images/ESGI/Langage_de_scripting_Shell_Python/Deplacer2.png)

Exemple:

![Exemple 1](http://portfolio.fpompey.com/images/ESGI/Langage_de_scripting_Shell_Python/Exemple1.png)

![Resultat](http://portfolio.fpompey.com/images/ESGI/Langage_de_scripting_Shell_Python/Exemple2.png)

**Méthodes:**

 - f.read() : lit tout le contenu du fichier f et le renvoie sous
 - forme de chaines de caractères.
 - f.readline() : lit une ligne du fichier.
 - f.readlines : lit tout le contenu du fichier et le renvoie sous forme d’une liste de chaines de caractères avec ‘\n’

 - f.write(chaine) : écrit la chaine indiquée dans le fichier
 - f.writelines(séquence) : écrit les chaines composant la séquence (liste, ensembles…) de chaines données dans le fichier f.
 - f.tell() : affiche la position où en est la lecture du fichier.
 - f.seek(n): permet de se déplacer au nième caractère (octet).

 - f.mode : renvoie le mode d'ouverture du fichier,
 - f.closed : True si le fichier est fermé, False sinon
 - f.name() : renvoie le nom du fichier
 - f.fileno() : est un numéro d'ouverture de fichier

 - f.close() : referme un fichier ouvert et enregistre un fichier créé ou édité ('w')
 - id( f ) : donne l'identifiant de la variable f.
 - hash(f ) : donne l'identifiant de la donnée contenue dans la variable f.

![Exemple 3](http://portfolio.fpompey.com/images/ESGI/Langage_de_scripting_Shell_Python/Exemple3.png)

![Resultat 2](http://portfolio.fpompey.com/images/ESGI/Langage_de_scripting_Shell_Python/Exemple4.png)
