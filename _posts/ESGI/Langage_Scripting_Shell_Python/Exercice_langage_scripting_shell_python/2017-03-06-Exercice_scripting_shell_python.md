---
layout: page
title:  "Exercices Langage de scripting Shell et Python"
teaser: "Exercices Langage de scripting Shell et Python lors de la semaine du 06 Mars 2017"
breadcrumb: false
tags:
    - esgi
    - langage_scripting_shell_python
    - cours
categories:
    - exercice_langage_scripting_shell_python
show_meta: false
---

# TP Pyhton

## Exerice 1 :

Tester, commenter et améliorer le code suivant :

    list1=["vendredi",19,"avril"]
    print(list1)
    print(list1[0])
    len(list1)
    list1.append(2012)
    print(list1)
    list1[3]+1
    del list1[0]
    print(list1)
    list1.insert(20,"Samedi")
    print(list1)
    print("jeudi" in list1)
    print("Samedi" in list1)
    list2=list1[1:3]
    print(list2)
    list3=list1[:2]
    list4=list1[1:]
    print(list3)
    print(list4)
    list3=list3+[2015]
    print(list3)
    list5=5*list1
    print(list5)
    list1.extend([3,4])
    print(list1)
    list6=list1.pop(0)
    print(list5)

Résultat :

    ['vendredi', 19, 'avril']
    vendredi
    ['vendredi', 19, 'avril', 2012]
    [19, 'avril', 2012]
    [19, 'avril', 2012, 'Samedi']
    False
    True
    ['avril', 2012]
    [19, 'avril']
    ['avril', 2012, 'Samedi']
    [19, 'avril', 2015]
    [19, 'avril', 2012, 'Samedi', 19, 'avril', 2012, 'Samedi', 19, 'avril', 2012, 'Samedi', 19, 'avril', 2012, 'Samedi', 19, 'avril', 2012, 'Samedi']
    [19, 'avril', 2012, 'Samedi', 3, 4]
    [19, 'avril', 2012, 'Samedi', 19, 'avril', 2012, 'Samedi', 19, 'avril', 2012, 'Samedi', 19, 'avril', 2012, 'Samedi', 19, 'avril', 2012, 'Samedi']

Correction :

    list1=["vendredi",19,"avril"] # Création d'une liste de 3 objets différents
    print(list1)                  # Affiche du contenu de la liste1
    print(list1[0])               # Affichage de 1er objet de la liste1
    **print (len(list1))**        # Affichage de la taille 3 de la liste1
    list1.append(2012)            # Ajout de l'objet entier 2012 à la fin (append = a la fin) de la liste1
    print(list1)                  # Affiche du contenu de la liste1
    list1[3]+1                    # Addition de l'objet entier 2012 et l'objet 1
    del list1[0]                  # Suppression de l'objet d'indice zero (vendredi)
    print(list1)                  # Affiche du contenu de la liste1
    list1.insert(20,"Samedi")     # Ajout de l'objet (samedi) à la fin de la liste(insert = à la 20ème position)
    print(list1)                  # Affiche du contenu de la liste1
    **print (list1[3])**          # Affichage et vérification de l'élément 4
    print("jeudi" in list1)       # Affichage de la vérification (jeudi est dans la liste = Faux)
    print("Samedi" in list1)      # Affichage de la vérification (samedi est dans la liste = Vrai)
    list2=list1[1:3]              # Créaion de la liste2 d'éléments 1&2 (3 exclus) à partir de la liste1
    print(list2)                  # Affichage du contenu de la liste2
    list3=list1[:2]               # Création de la liste3 d'élements 0 à 1 (2 exclus) à partir de la liste1
    list4=list1[1:]               # Création de la liste4 d'éléments 1 à la fin à partir de la liste1
    print(list3)                  # Affichage du contenu la liste3
    print(list4)                  # Affichage du contenu de la liste4
    list3=list3+[2015]            # Ajout de l'objet (2015) à la liste3
    print(list3)                  # Affichage de la liste3
    list5=5*list1                 # Création de la liste5, 5 fois la liste1
    print(list5)                  # Affichage de la liste5
    list1.extend([3,4])           # Ajout à la liste1 l'élément 3 et 4
    print(list1)                  # Affichage de la liste1
    list6=list1.pop(0)            # Création de la liste6 en suppression de l'élément d'indice zero (19)
    **print(list6)**              # Affichage de la liste6
    **print(list1)**              # Affichage de la liste1

Résultat :

    ['vendredi', 19, 'avril']
    vendredi
    3
    ['vendredi', 19, 'avril', 2012]
    [19, 'avril', 2012]
    [19, 'avril', 2012, 'Samedi']
    Samedi
    False
    True
    ['avril', 2012]
    [19, 'avril']
    ['avril', 2012, 'Samedi']
    [19, 'avril', 2015]
    [19, 'avril', 2012, 'Samedi', 19, 'avril', 2012, 'Samedi', 19, 'avril', 2012, 'Samedi', 19, 'avril', 2012, 'Samedi', 19, 'avril', 2012, 'Samedi']
    [19, 'avril', 2012, 'Samedi', 3, 4]
    19
    ['avril', 2012, 'Samedi', 3, 4]

## Exerice 2 :

Définir la liste : list=[17,20,38,26,68,45]
Effectuer les actions suivantes :
 - Trier et afficher la liste
 - Ajouter l’élément 17 puis afficher
 - Calculer le nombre d’apparition de l’élément 17
 - Renverser et afficher la liste
 - Afficher la taille de la liste
 - Afficher l’indice de l’élément 10
 - Enlever l’élément 38 et afficher la liste
 - Afficher le sous liste du 3ieme au 4ieme élément
 - Afficher la sous liste du début au 2ieme élément
 - Afficher la sous liste du 3ieme liste à la fin de la liste
 - Afficher le dernier élément en utilisant un indiçage négatif

Resultat (en cours):

    list=[17,20,38,26,68,45] # Définis la liste
    print(list)              # Affiche la liste
    list.sort()              # Tri la liste
    print(list)              # Affiche la liste
    list.append(17)          # Ajout de l'élément 17 à la fin de la liste
    print(list)              # Affiche la liste
    print(list.count(17))    # Affiche le nombre d'occurence de l'élément 17
    list.reverse()           # Inverse la liste
    print(list)              # Affiche la liste
    print(len(list))         # Affichage de la taille de la liste
    # print(list[10])          # Affichage de l'élément dans la liste
    list.del(30)
    print(list)


## Exerice 3 :

Utiliser une liste en intension pour obtenir la liste [ad,ae,bd,be,cd,ce] à partir des chaînes abc et de en utilisant une version en extension avec deux boucles for imbriquées, puis une version en intension.

## Exerice 4 :

Ecrire une fonction nbr_mots qui admet comme argument une chaîne de caractères et qui renvoie un dictionnaire contenant la fréquence d’apparition de chaque mot de la chaîne.     
Exemple « Mais ou est passé Paul ? Paul est au ciné »

    Donc Dico[paul]=2

## Exercice 5 :

1. Proposer une implémentation d’un annuaire de gestion des utilisateurs d’un réseau local avec le minimum (login/Password) avec le password hashé MD5.
2. Justifier le choix de la structure de données.

Minimum fonctionnel attendu : Création/consultation/MAJ et la suppression d’un user.
