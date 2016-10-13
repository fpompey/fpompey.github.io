---
layout: page
title:  "Exercice Architecture Reseaux"
teaser: "Exercice Architecture Reseaux lors de la semainedu 10 Octobre 2016"
breadcrumb: false
tags:
    - esgi
    - architecture_reseaux
    - exercice
categories:
    - exercice_architecture_reseaux
show_meta: false
---

<!-- TOC depthFrom:1 depthTo:6 withLinks:1 updateOnSave:1 orderedList:0 -->

- [**Exercice 1:**](#exercice-1)
- [**Exercice 2:**](#exercice-2)
- [**Exercice 3:**](#exercice-3)
- [**Exercice 4:**](#exercice-4)
- [**Exercice 5:**](#exercice-5)
- [**Exercice 6:**](#exercice-6)
- [**Exercice 7:**](#exercice-7)
- [**Exercice 8:**](#exercice-8)
- [**Exercice 9:**](#exercice-9)
- [**Exercice 10:**](#exercice-10)
- [**Exercice 11:**](#exercice-11)
- [**Exercice 12:**](#exercice-12)
- [**Exercice 13:**](#exercice-13)
- [**Exercice 14:**](#exercice-14)
- [**Exercice 15:**](#exercice-15)
- [**Exercice 16:**](#exercice-16)
- [**Exercice 17:**](#exercice-17)
- [**Exercice 18:**](#exercice-18)
- [**Exercice 19:**](#exercice-19)

<!-- /TOC -->

# **Exercice 1:**

Parmi les mécanismes suivants :

    1. contrôle d’accès au support (Media acces control MAC)
    2. contrôle de flux
    3. reprise sur erreur
    4. gestion de la fenêtre d’anticipation
    5. gestion du multiplexage
    6. routage des paquets
    7. filtrage des adresses MAC
    8. transport de paquets ICMP

Quels sont ceux mis en œuvre par:

    1. IPv4
    2. TCP
    3. UDP


IPv4 :
1. contrôle d’accès au support
6. routage des paquets
7. filtrage des adresses MAC
8. transport de paquets ICMP

TCP :
2. contrôle de flux
3. reprise sur erreur
4. gestion de la fenêtre d’anticipation
5. gestion du multiplexage

UDP :

4. gestion de la fenêtre d’anticipation

# **Exercice 2:**

Quels sont les services complémentaires fournis par:

    UDP par rapport à IP?
    TCP par rapport à IP?

# **Exercice 3:**

Au niveau d’un récepteur, quel est le protocole qui:

    Détecte la non réception
      D’un paquet
      D’un fragment
    Demande la retransmission
      D’un paquet
      D’un fragment

# **Exercice 4:**

Sur un même réseau, une station A doit connaître l’adresse MAC de la station B dont elle connaît l’adresse IP pour communiquer avec elle.  
Comment procède –t-elle?

# **Exercice 5:**

Pour quelles raisons un administrateur décide de segmenter son réseau en plusieurs sous-réseaux?

# **Exercice 6:**

Comment sont traitées les entêtes IPv4  si l’émetteur et le récepteur sont:

    Sur le même sous-réseau?
    Sur deux réseaux distincts?

# **Exercice 7:**

Quelle est l’intérêt des adresses sans classe (CIDR)?

# **Exercice 8:**

De quelles informations dispose-t-on pour déduire qu’un datagramme contient un fragment?

Une passerelle peut-elle confondre deux fragments qui ont les mêmes  adresses et le même numéro de fragment?

# **Exercice 9:**

Dans le cas d’un hôte présentant l’adresse IP 172.32.65.13 et un masque de sous-réseau par défaut, à quel réseau ci-dessous l’hôte appartient-il?

    1. 172.32.65.0	 	
    2. 172.32.65.32
    3. 172.32.0.0   		
    4. 172.32.255.255

# **Exercice 10:**

Soient l’adresse IP 192.100.10.70 et le masque de sous-réseau 255.255.255.240, donnez:

1. Le netid et l’adresse IP du réseau
2. Le hostid et l’adresse IP de la machine
3. Le nombre maxi possible de sous-réseaux
4. Le nombre maxi possible de stations par sous-réseau
5. L’adresse de broadcast sur le sous-réseau 128

Les adresses IP des machines du sous-réseau 128 vont de quelle adresse à quelle adresse?

**Réponse:**

1.Grace au premier octet de l'IP **192** nous savons que le réseau appartient à la classe C  
pour notre IP => Net ID = 192.100.10  
L'adresse IP de de réseau est 192.100.10.0 grâce au masque qui est 255.255.255.240 => /28


    Le masque en binaire  
    11111111.11111111.11111111.11110000

2.Le Host ID est 6, le masque est 240, sur les 8 derniers bits seul les 4 derniers sont dédiés aux machines, les bit à 1 correpondent alors à 4 et 2 donc = 6)

Pour déterminer l'IP de la machine on a en binaire :  

    IP machine :     192.168.10.   0100/0110 (70)  
    Masque réseau :  255.255.255.  1111/0000 (240)  
    Avec le ET logique, on obtient  0100/0000 (64)  

L'adresse IP de la machine est donc 192.168.10.64

3.Le nombre maxi possible de sous-réseaux est lié au masque /28 donc il n'y aura que les 4 derbiers bits qui seront pris en compte  
Le calcul :

    2^4 = 16

Il y aura doncc 16 sous réseaux possible au maximum.

4.Le nombre maxi possible de machines est identique au raisonnement précédent - addresse de réseau - addresse de broadcast  
Le calcul:

    (2^4 -2 = 14)

Il y aura donc 14 machines possible au maximum dans ce réseau.

5.L'adresse de broadcast est 192.100.10.143 (le bit du réseau qui est 128 auquel on ajoute les 4 bits à 1 des machines donc 128+15)   
Le calcul pour un broadcast, tout les bits en dehors du masque passent à 1, les autres sont ignorés donc à 0:

    IP : 192.100.10.128  
    En binaire les 8 derniers bits : 10000000  (128)
    Masque : 255.255.255.240  
    En binaire les 8 derniers bits : 00001111  (15)
    Avec le OU logique, on obtient : 10001111  (128+15 = 143)

# **Exercice 11:**

Deux réseaux A et B sont reliés par un routeur.  
L’entreprise à défini le masque 255.255.0.0.    
Un utilisateur du réseau A sur la machine 100.64.0.102 se plaint de ne pouvoir joindre un utilisateur du réseau B d’adresse 100.64.45.102.

Expliquez pourquoi ?

**Réponse:**  
D'après les mêmes adresses IP, A et B sont sur le même sous réseau 64, or physiquement, elles sont dans deux sous réseaux distincts, donc erreur de routage.
Pour résoudre le souci on pourrait changer les adresses IP ou le masque.


# **Exercice 12:**

Parmi les adresses suivantes déterminez celles qui peuvent être utilisées pour les hôtes des sous-réseaux du réseau 200.100.50.0 dont le masque est 255.255.255.240:

    1. 200.100.50.100       
    2. 200.100.50.80
    3. 200.100.50.208

# **Exercice 13:**

Une entreprise possède 4 succursales et utilise l’adresse 200.30.26.0.  
Pour mieux  gérer les sous-réseaux, le responsable informatique souhaite attribuer une adresse IP propre à chaque sous-réseau  des 4 succursales.  

De quelle classe d’adresse s’agit-il?

Donnez le masque de sous-réseau correspondant ?

Donnez le nombre maximum de machines par sous-réseau ?

Donnez l’adresse de  broadcast  pour chaque  sous-réseau ?

# **Exercice 14:**

Une station a émis un datagramme IP de 1300 octets de données.  
Le réseau WAN traversé est en mode connecté et n’accepte que des paquets de 64 octets.

Représentez le diagramme des échanges ?

# **Exercice 15:**

Un routeur reçoit un paquet IPv4 de 4000 octets de données d’un FDDI et doit le router vers un segment Ethernet.  
L’entête du paquet IP reçu est:

    Identif = 3426, longueur = 4020, DF = 0, MF = 0, PF=0

Donnez les entêtes des différents fragments issus du paquet IP ?

# **Exercice 16:**

A partir d’une station d’adresse IP 193.18.24.5 vous lancez les commandes suivantes:

    Ping 127.0.0.1
    Ping 193.18.24.10
    Ping 150.40.45.32

Selon le résultat obtenu, qu’est ce que l’on peut déduire?

# **Exercice 17:**

Soit un réseau de 4 machines dont les adresses  sont:

    Vénus		    10.99.43.27		  mac-1
    Jupiter	    10.163.12.200		mac-2
    Mars		    10.189.12.27		mac-3
    Terre		    10.126.43.234		mac-4

1. Quel est le netid de ce plan d’adressage?

2. Quel est le nombre de bits, minimum et maximum, nécessaire pour que vénus et terre soient sur le sous-réseau A , jupiter et mars soient sur le sous-réseau B ?  
Donnez les masques correspondants.

3. Quel est le nombre de bits minimum pour que les 4 machines soient sur des sous-réseaux différents ?   
Donnez le masque correspondant.

4. Donnez le contenu de la table ARP de vénus en considérant que nous sommes dans la configuration de la question 2.

**Réponse:**

1.Le NetId de ce plan d'adressage est **10**, il est lié au premiet octect "10" qui correspond à la classe A, le second octect étant différent sur les autres IP du réseau.

2.Il faut convertir en binaire pour identifier combien de bits sont nécéssaire au minimum et maximum pour être dans la classe A et B

    Vénus : 10.99.43.27 => 00001010.01100011.43.27
    00001010 (10)
    01100011 (99)

    Jupiter : 10.163.12.200 => 00001010.101000011.12.200
    00001010 (10)
    10100011 (163)

    Mars : 10.189.12.27 => 00001010.10111101.12.27
    00001010 (10)
    10111101(189)

    Terre : 10.126.43.234 => 00001010.01111110.43.234
    00001010 (10)
    01111110 (126)

Il faut donc au minimum 7 bits pour avoir l'addresse de classe A entre Vénus et Terre (0000101/0)  
masque = 254.0.0.0 => /7

Il faut donc au maximum 8 bits pour avoir l'adresse de classe A (Une adresse IP de classe A dispose d'une partie net id comportant uniquement un seul octet)  
masque = 255.0.0.0 => /8

Il faut donc au minimum  11 bits pour avoir l'adresse de classe B entre Jupiter et Mars.  
masque = 255.224.0.0  => /11

Il faut donc au maximum 16 bits pour avoir l'adresse de classe B (Une adresse IP de classe A dispose d'une partie net id comportant uniquement deux octet)  
masque = 255.255.0.0 => /16

3.Il faut au minimum 12 bits pour que les 4 machines soient sur des sous-réseaux différents (dernier bits différents de tous les réseaux en binaire)

# **Exercice 18:**

Décoder la trame Ethernet suivante et dire pourquoi le paquet IP transporté est plus long que prévu dans l’entête?

    08 00 20 01 b4 32 08 00     20 00 61 f3 08 00 45 00
    00 2c 0c 30 00 00 1e 06     b0 79 c0 09 c8 0b c0 09
    C8 01 04 05 00 15 00 06     e8 01 00 00 00 00 60 02
    10 00 bd 4d 00 00 02 04     04 00 00 00

# **Exercice 19:**

Les adresses IPv6 sont hiérarchiques.  
Expliquez.

1.Qu’indique le contenu du champ FP (Format  Prefix ) ?  
Donnez le format compressé de cette adresse

    0:0:0:0:0:0:0:1

2.Que représente l’adresse suivante ?

    0:0:0:0:0:0:195:200:100:12

3.Trouvez l’erreur:

    1abc::fec3:2bf::1

4.Quel est le point commun entre une adresse privée IPV4 et une adresse locale de site IPV6?


**Réponse :**

1.Le champ FP indique  
L'adresse  0:0:0:0:0:0:0:1 peut être compressée en ::1 car en IPV6 on peut remplacer les suites de zéros par un "::". Toutefois on ne peut le faire qu'une seule fois par adresse, afin que le routeur sache remplacer par le bon nombre d'octets.

2.

3.On a pas le droit de mettre deux fois les "::" dans une adresse IPV6, car il devient impossible de savoir combien de 0 sont contenus dans les "::".

4.Les adresses locales de site IPV6 respectent la notation CIDR, comme les adresses privées d'IPV4. (On sait à quelle région géographique les adresses appartiennent).
