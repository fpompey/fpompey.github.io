---
layout: page
title:  "Exercice Linux TP1"
teaser: "Exercice Linux TP1 lors de la semainedu 10 Octobre 2016"
breadcrumb: true
tags:
    - esgi
    - linux
    - exercice
categories:
    - exercice_linux
show_meta: false
---

# **Question 1**

Lire le manuel de "ls" pour expliquer le résultat de la commande suivante :

    $ ls -srF /etc

**Réponse :**    
-F ajoute un caractère (parmi \*/=>@| ) à chaque entrée  
-r inverse l'ordre du tri (sans paramètre il était en ordre alphabétique, ça sera donc l'inverse ici)  
-s affiche la taille allouée à chaque fichiers en nombre de blocs  
Et cette commande s'appliquera sur le répertoire /etc  


# **Question 2**

Donner une commande qui affiche :

        Hello <user>, welcome on <host> avec <user> et <host> remplacés par le nom de l’utilisateur actif et par le nom de la machine.

**Réponse :**  

echo « Hello $USER, welcome on $HOSTNAME »


# **Question 3**

Lister les fichiers présents dans tous les répertoires du PATH.   
Noter les 3 premiers de chaque répertoire.   
Trouver l’emplacement du programme info.
Pouvez vous trouver l’emplacement de cd et echo ?  
Pourquoi ?

# **Question 4**

Donner une commande permettant de créer l’arborescence

        $HOME/a/b/c/d/e/f/

en une seule ligne (regarder la page info de mkdir).

**Réponse :**

mkdir -p $HOME/a/b/c/d/e/f/


# **Question 5**

Créer le fichier vide test1 dans

    $HOME/a/b/c/d/e/f/

et les fichiers vides test2 et test3 dans

    $HOME/a/b/c/d/.

Supprimer le répertoire

    $HOME/a/b/c/d/e.

Qu’est devenu le fichier test1 ?

# **Question 6**

Modifier l’arborescence pour obtenir

    $HOME/a/c/d/

sans perdre les fichiers test2 et test3 dans d/ (b doit être supprimé).

# **Question 7**

Donner la taille de /bin/cat de façon "humaine", c’est à dire en Ko, en Mo ou en Go selon la taille du fichier (info ls).

# **Question 8**

Faire en sorte que :

    $ cd ls doc

liste le contenu le /usr/share/doc.

# **Question 9**

Récupérer tp1-files.tar.gz.   
Décompressez l’archive.   
Les extensions des fichiers à l’intérieur ne correspondent pas au type de leur véritable contenu.   
Remettre les bonnes extensions.
Pour télécharger l’archive, taper les commandes suivantes :

# **Question 10**

Créer une archive modules.tar.gz contenant le répertoire /lib/modules, qui en se décompressant crée un répertoire modules/ avec le contenu de /lib/modules dedans. Exemple de décompression :

    $ tar xfz modules.tar.gz
    $ cd modules
    $ ls

La sortie du dernier ls doit être équivalente à :

    $ cd /lib/modules
    $ ls

# **Question 11**

Supprimer tous les répertoires créés dans $HOME.

# **Question 12**

Monter la partition Windows du disque dur de la machine dans le répertoire /mnt/windows.  
Donner la ligne contenant

    execstd

dans le fichier

    C :\windows\system\setup.inf.

Attention, ces commandes doivent être exécutés sous l’identité de l’administrateur "root".  
Pour changer d’utilisateur, utiliser la commande su.   
Penser à retourner en utilisateur normal après ces commandes (commande exit).

# **Question 13**

  **Etape 1**

Donner une commande qui liste les fichiers/répertoires de /usr/share/doc en excluant :

1. Les fichiers commençants par "lib"
2. Les fichiers commençants par les lettres a,b,c,d,e,s,x

  **Etape 2**

Comment peut-on combiner la commande de l’étape 1 avec tar pour créer une archive

    $HOME/mydoc.tar.gz

contenant tous les fichiers/répertoires de /usr/share/doc à l’exception de ceux cités à l’étape 1 ?
