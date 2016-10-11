---
layout: page
title:  "Procédure d'installation github via Atom"
teaser: "Cette procédure a été faite dans le cadre de ma première année dans la société BCS Technologies, elle a subi plusieurs modification à la suite des différents avis lors de ma seconde année."
breadcrumb: true
tags:
    - procedure
    - atom
    - github
categories:
    - procedure
show_meta: false
---

# **Github pour Windows**

**Présentation générale**

Atom est un editeur de texte comme le bloc notes sur windows qui est très personalisable et compatible avec github avec lequel on va travailler.

**Mise en place**

Cette application va être içi pour récuperer tous vos projets lié à votre compte github, il faut donc bien évidemment un compte puis télécharger l'application [içi](https://desktop.github.com/)

Il faut mettre le mail utilisé pour github ainsi que le mot de passe.
![Setup](https://fpompey.github.io/images/Atom/Setup_Github_for_windows.png)

Dans l'onglet Configure choisir le chemin ou va être installé le projet que vous souhaité récupéré sur votre machine en local.

Si vous avez fait une erreur ou besoin de modifier une information vous avez les options qui se trouve en haut à droite sur la page d'acceuil.

Une fois que tout est configuré vous pouvez récupéré le repository désiré (clone) ou crée un nouveau (create)

Le repository devrait maintenant apparaitre dans votre barre de navigation sur la gauche.

Il faut régulièrement s'assurer que votre projet est bien à jour pour cela il faut synchroniser votre repository avec github

![Synchronisation](https://fpompey.github.io/images/Atom/History_projet_github.png)

Vous avez maintenant votre projet en local sur votre machine

# **Git pour Windows**

Pour pouvoir utiliser les packages git sur Atom il va falloir installer les dépendances nécéssaires pour son bon fonctionnement.

Il faut donc aller [içi](https://git-for-windows.github.io/)

Lors de l'installation choissiser bien l'option qui va directement mettre en place les **PATH** (chemin d'accès) qui vont être utilisé par GIT, choissisez ensuite le répértoire dans lequel vous voulez l'installer.

# **Atom**

Maintenant que git est bien installé sur votre poste en local et que votre projet est à jour avec tous les fichiers nécéssaires, il faut installer Atom [içi](https://atom.io/).

Une fois l'installation effectué lancer Atom.  

Dans Settings > Project Home assurez vous bien que le chemoin mène à votre repository github (projet).  

    File > Add Project Folders > Votre_Projet

Vous devriez maintenant le voir dans l'outil de navigation sur la gauche.

Je vous recommande d'installer cette liste de packages qui me semble nécéssaire, aller dans

    File > Settings > Install > (NOM)

1. git-log
2. git-plus
3. git-time-machine
4. highlight-selected
5. markdown-pdf
6. markdown-preview
7. mardown-toc
8. seti-icons
9. tree-view-git-branch
10. tree-view-git-status
11. pdf-view
12. minimap
13. minimap-find-and-replace
14. minimap-pigments

Je vous invite malgré tous à vous rendre sur la page du package pour vérifier si il vous semble intéressant. (Package indispensable git-plus).
