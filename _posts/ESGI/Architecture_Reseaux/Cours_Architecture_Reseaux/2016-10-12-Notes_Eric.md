---
layout: page
title:  "Notes Eric"
teaser: "Notes Eric lors de la semainedu 10 Octobre 2016"
breadcrumb: false
tags:
    - esgi
    - architecture_reseaux
    - cours
categories:
    - cours_architecture_reseaux
show_meta: false
---

IPV6 est plus sécurisé que l'IPV4.
La ou il faut ajouter l'IPsec (sécurisé) à l'IPV4, l'IPV6 l'inclut nativement.
L'IPsec permet de supporter les VPN.


TCP contient un compteur pour s'assurer que les données sont toutes bien envoyées.
Si le numéro d'acquitement est différent du compteur, c'est un acquitement négatif
On recommence le transfert à partir du numéro du compteur (qui correspond à un octet).


Tous les ports dont le numéro est inférieur à 1023 sont réservés.


EOM = Fin fichier = Fin message.  
Si le buffer est plein, les données s'envoient. Mais si on arrive à la fin et qu'il n'y a pas assez de données pour remplir le buffer, le flag PSH envoie le EOM pour qu'on envoie les données.


Le controle de flux, c'est pour éviter les pertes de données. (il est présent dans TCP)


Avantage d'UDP par rapport à IP:
transmission vers les applications à l'aide des ports + checksum sur les données et pas seulement sur les entêtes.
UDP c'est une couche transport alors qu'IP c'est la couche réseau.
