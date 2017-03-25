---
layout: page
title:  "Cours Algorithme avancée"
teaser: "Cours Algorithme avancée lors de la semaine du 10 Octobre 2016"
breadcrumb: false
tags:
    - esgi
    - algorithme
    - cours
categories:
    - cours_algorithme_avancee
show_meta: false
---

<!-- TOC depthFrom:1 depthTo:6 withLinks:1 updateOnSave:1 orderedList:0 -->

- [Structure de données](#structure-de-donnes)
	- [Comment évoluer un algo ?](#comment-voluer-un-algo-)
	- [Définition:](#dfinition)

<!-- /TOC -->

# Structure de données
  1. Tableau
  2. Liste/pile/file
  3. arbre (AB,ABR,AB+)
  4. Graphe
  5. coucou ca va bien ?

## Comment évoluer un algo ?
  1. Calcul de complexité
  2. Récursivité

**Tableau**

Un tableau est une collection de données de même type ordonnée, indexée, contiguess en mémoire.  
t= [e1, e2, e3] &forall;i, ei &isin; N , taille finie

**Ensemble**

*Algo:* tri selection, tri à bulles, tri fusion  
Collection d'élements de même type, taille finie / infinie, non ordonné,les doublons  
{1,3,2} = {1,3,2}

Tri naïf/séléction => Recherchez le minimum dans tout le tableau, et le permutez avec la 1ère case une fois le minimum trouvé. Recommencez l'opération sans utiliser le premier nombre qui a été trouvé.
Continuez jusqu'à avoir un ordre croissant dans sa suite

Tri a bulle => Le premier nombre va se comparer au nombre suivant celu-ci.   
Si le nombre est inférieur au nombre source, il permute jusqu'à se rendre au dernier nombre.  
Continuez jusqu'à avoir un ordre croissant dans sa suite.

**Liste**

Collection d'élements de même type, taille finie / infinie, ordonnée les doublons  
{1,3,2} &ne; {1,2,3} &ne; {1,2,3,4}

**Arbre**

Collection d'élements avec une relation d'ordre, un ensemble de noeusds avec un ensemble d'arête et de pic

## Définition:

taille = nombre de noeuds  
hauteur = nombre de branches qui separent la racine de la feuille la plus éloigné (hauteur de l'arbre vide = -1)   
racine = noeud qui n'as pas de père  
feuille = noeud qui n'a pas de fils (noeud externe)  
noeud interne = noeud qui ont des fils  
arité = nombre max de fils que peut avoir un noeud (lorsque l'arite = 2 => arbre binaire, lorsque l'arite = 3 => Arbre ternaire ...)  

N'importe quel arbre peut être transformé en arbre binaire équivalent.

LC = Longueur de cheminement = &sum; hi(hauteur) x ni(nombre de noeuds)  
LCI = Longeur de cheminement interne = &sum; hi(hauteur) x ni(nombre de noeuds) (interne)  
LCE = Longeur de cheminement externe = &sum; hi(hauteur) x ni(nombre de noeuds) (externe)

LC = LCI + LCE

Parcours en largeur = On liste tous les noeuds de gauche àdroite niveau par niveau

Definition récursive = Possède au moins:
  1. Une condition d'arret
  2. Une partie qui s'auto appelle

Définition récursive de l'arbre binaire:

  1. Soit l'arbre est vide  
  2. Soit l'arbre est constitué d'une racine, d'un arbre à gauche, d'un arbre à droite

ABR = Arbre binaire de recherche:
  1. Tous les noeuds dans une partie gauche sont plus petits que la racine
  2. Tous les noeuds dans une partie droite sont plus grands que la racine

Parcours en largeur => Lister les noeuds niveau par niveau de gauche à droite.

Parcours préfixe => r g d

Parcours postfixe => g d r

Parcours infixe => g r d

On écrit le noeud si on est sur **r** sinon on est sur un arbre et on reappelle le parcours (Récursif)
