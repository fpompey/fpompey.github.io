---
layout: page
title:  "Procédure Routage & VLAN"
teaser: "La MFC (Maison de la Formation Continue) réside à l'IMCP (Paris), notre objectif est d'administrer le réseau de notre filiale."
breadcrumb: true
tags:
    - procedure
    - Routage
    - VLAN
categories:
    - procedure
show_meta: false
---

### Contexte ###

La MFC (Maison de la Formation Continue) réside à l'IMCP (Paris) et est administré par le professeur de réseau de l'école. 
La MFC nous fournit un réseau internet via une borne d'accès WIFI TP Link ainsi qu'un routeur NetGear. On a également accès à leur infrastructure avec des postes fixes Windows et Linux, ainsi qu'un serveur ESXI pour virtualiser nos machines.
Nous sommes une filiale qui intéragit avec le siège de la MFC. 
Notre objectif est d'administrer le réseau de notre filiale, pour cela nous disposons de 3 switchs D-Link, 1 routeur NetGear et une borne wifi TP-Link.

Dans cette partie, nous allons parler du routage ainsi que des VLAN.
Pour respecter le contexte de la **MFC**, nous devons avoir quatre **VLAN**  qui sont :

 - VLAN administratif   (VLAN 2)
 - VLAN formation       (VLAN 3)
 - VLAN Wifi            (VLAN 400)
 - VLAN DMZ             (VLAN 4)

Notre réseau pour la filiale Nantes est 10.40.x.x/16
Le découpage IP de l'infrastructure est visible sur le visio.

![alt text](https://fpompey.github.io/images/MFC_Routage_VLAN/Visio.png "Visio")

 
### Etape 1 Routeur ###

Dans une première étape, nous avons mis à jour le firmware, nous avons saisi les IP que nous avons établis au préalable sur le visio. 
Ensuite, nous avons créé les utilisateurs autorisés à se connecter à la filiale Nantes. 
Enfin, il nous a fallu activer l'inter VLAN pour pouvoir établir la communication entre les différentes VLAN créer auparavant.

![alt text](https://fpompey.github.io/images/MFC_Routage_VLAN/Routeur.png "Routeur")

### Etape 2 WIFI ###

Premièrement, nous avons établi le nom SSID de cette façon [RESEAU]-[NOM_FILIALE]-[LIEU] = WIFI-NANTES-IMCP
Nous avons ensuite choisi une clé WPA2-PSK qui est actuellement la norme la plus sécurisée sur notre borne.
Nous avons ensuite choisi l'IP et la passerelle en respectant le visio.

![alt text](https://fpompey.github.io/images/MFC_Routage_VLAN/WIFI.png "WIFI")

### Etape 3 Switch ###
Puis, nous avons configuré les switchs. Nous avons tout d'abord saisi l'IP et la passerelle.
Ensuite, nous avons créé les VLAN par port et activé le port based VLAN.
Enfin, nous avons procédé à un test de configuration, afin de vérifier que la communication dans un même VLAN ainsi que la communication inter VLAN fonctionne correctement. 

![alt text](https://fpompey.github.io/images/MFC_Routage_VLAN/Switch.png "Switch")

// Nous avons créé les VLAN via la norme 802.1Q VLAN. 
// Enfin, nous avons activé le management VLAN en l'associant au VLAN administratif ainsi que le port trunking qui servira à associer plusieurs ports comme si s'agissait d'un seul afin de communiquer avec les différents VLAN.

 
