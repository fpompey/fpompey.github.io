---
layout: page
title:  "Procédure IPMonitor"
teaser: "Cette procédure a été faite dans le cadre de ma première année dans la société BCS Technologies, elle a subi plusieurs modification à la suite des différents avis lors de ma seconde année."
categories:
    - P1
tags:
    - P1
    - Procedure
header: no
---

# IPmonitor #

Tout le monitoring que l’on peut retrouver sur ipmonitor, sont des potentiels alertes qui permettront à la personne d’astreintes d’identifier au mieux le problème afin de le résoudre rapidement.

Il faut donc qu’il soit le plus **complet** possible et que tous les compteurs mis en place soit **testé** au préalable afin de ne pas avoir de faux positif lors des astreintes ou au contraire qu’on ne soit pas suffisamment alerté.

Essayer de respecter au mieux la même mise en forme que sur le reste des compteurs.

*Exemple*

    [MACHINE][NOM_COMPTEUR][TYPE_COMPTEUR]

**A Retenir:**
- Tout les compteurs Drivespace mis en place qui peuvent fonctionner en 24x7 doivent avoir un compteur HO a 15% et le compteur drivespace qui sera 24x7 à 5% (A adapter selon la taille de la partition, exemple une partition de 15Go sera plus à 10% ou 8% soit environ 1G afin de pouvoir agir avant saturation du drivespace) Cela permettra d'être avertie en HO si c'est une augmentation normale (HO lente et progressive) ou brutal (24x7).
- Tout les compteurs *Custom:SNMP* que vous allez mettre en place vont nécéssiter un OID du type 1.3.6.1.4.1. Chaque équipement aura un OID qui pourra varier selon le compteur CPU/MEMORY ou autre ... Il faudra donc noter la marque de l'équipement et rechercher l'OID qui correspond à votre compteur

Exemple: Power supply Alarm PDU APC 1.3.6.1.4.1.318.1.1.12.4.1.3.0

## Machine Windows ##
Pour toutes les machines physique il faut ajoutter le compteur DRAC

### Applicatif ###
Ces machines sont surtout réservé à un type d’application
En fonction de l’applicatif mis en place, il faudra adapter les compteurs pour surveiller au mieux l’applicatif.
Il faut impérativement mettre en place :
- PING
- PHYSICAL MEMORY
- CPU
- DRIVESPACE qu’utilisent la machine *(souvent le [C:\] et [D:\])*
- Service associé à l'applicatif

### Backup ###
Ces machines sont presque toute sous Windows, les soft principalement utilisé sont **VEEAM** et **BACKUP EXEC**.
Il faut impérativement mettre en place :
- PING
- PHYSICAL MEMORY
- CPU
- DRIVESPACE qu’utilisent la machine *(souvent le [C:\] et [D:\])*
- Service utilisé par le soft(VEEAM et BACKUP EXEC)

## Machine Unix ##
Pour toutes les machines physique il faut ajoutter le compteur DRAC.

### Applicatif ###
Ces machines sont surtout réservé à un type d’application *(WEB, MYSQL, CACHE, Applicatif)*.
En fonction de l’applicatif mis en place, il faudra adapter les compteurs pour surveiller au mieux l’applicatif.
Il faut impérativement mettre en place :
- PING
- MEMORY
- CPU
- Les partitions qu’utilisent la machine *(souvent le [/] et [/var/www]*
Lors du monitoring il faut surtout faire attention a ne pas rajoutter des compteurs de drivespace inutile (ipmonitor à une limitte de compteur qu'il peux crée). Il ne faut donc pas ajoutter les partition comme /dev /run /sys [/boot /tmp] (Ces deux là ne doivent pas être monitoré sur ipmonitor mais peuvent être graphé sur Cacti pour avoir un aperçu)

### Base de donées ###
Ces machines sont presque toutes sous Unix *(mysql, postgresql, oracle)*.
En fonction de la base de données utilisée les compteurs devront être adapté en conséquences.
Il faut impérativement mettre en place:
- PING
- PHYSICAL MEMORY
- CPU
- Les partitions qu’utilisent la BDD *(comme [/] [/srv] [/var] …)*
Pour savoir qu'elle partition est utilisé connecter vous à la machine et effectuer
        df -h

## Autre ##

### ESX ou Baie de Stockage ###
Généralement on monitore
- PING
- DRAC
- CPU
- DRIVESPACE de l’ESX.

### VCenter ###
Généralement si le Vcenter est accessible en ligne
- PING
- HTTP
- HTTPS

### Firewall ###
Ces machines sont principalement des fortigates
Généralement on monitore
- PING
- HTTPS
- HTTP
- CPU
- Compteur de bande passante utilisé *(BANDWITH)*
Si les firewall sont en Cluster il faut ajoutter un compteur Master et Slave.

### FortiAnalyser ###
Ces machines sont principalement des fortigates
Généralement on monitore
- PING
- HTTP
- HTTPS
- CPU
- Compteur de bande passante utilisé *(BANDWITH)*
- Internal Flash Disk Drivespace
- Compact Flash Disk Drivespace

### Switch ###
Généralement on monitore
- PING
- CPU
- Memory
- Compteur de bandes d'etat de port [link up] *(OID 1.3.6.1.2.1.2.2.1.8.)*
- Compteur de bandes d'erreur de port [in errors] *(OID 1.3.6.1.2.1.2.2.1.14.)*


### Contacteur Portes ###
Il sont mis en place afin de surveiller si la baie est ouverte sans autorisation.
Généralement on monitore
- PING
- Contacteur de la porte
- HTTP

### PDU ###
On monitore
- PING
- POWER SUPLY ALARM

# CACTI #

Tout le monitoring que l'on peux retrouver sur Cacti est utilisé à titre **d'information**. Il ne remonte aucune alerte.

Il est avant tout présent afin de voir l'historique de la machine et l'évolution dans le temps comme un esapce disque qui évolue progressivement.

**Chaque compteurs figurant sur Ipmon doit être graphé avec Cacti.**

## Machine Windows ##
En général les template associé sont :

**Associated Graph Template**
- Host MIB - Logged in Users
- Host MIB - Proceses
- SNMP Informant - Memory Usage

**Associated Data Queries**
- SNMP - Get Mounted Partitions
- SNMP - Get Processor Information
- SNMP - Interfce Statistics
- W32 - CPU Statistics

**Data Query [SNMP - Get Mounted Partitions]**

Toutes les partitions que possèdent la machine, principalement
- C:
- D:
- Virtual Memory
- Physical Memory

**Data Query [SNMP - Interface Statistics]**

On graph le traffic, voir les ports up pour les graphs.
- In/Out Bits
- Default - In/Out Errors/Discarded Packets
- Default - In/Out Unicast Packets

**Data Query [W32 - CPU Statistics]**

- CPU total Uniquement (Inutile de Graph par CPU sauf si la demande est précisé sur les SQL)

**Data Query [W32 - Memory Statistics]**

## Machine Unix ##
En général les template associé sont :

**Associated Graph Template**
- BCS Probe - Memory
- BCS Probe - Swap (Si swap présent sur la machine)
- ucd 20 Processes
- ucd/net - Full CPU Usage
- ucd/net - Load Average
- Unix - Logged in Users

**Associated Data Queries**
- RFC1213 Statistics
- SNMP - Get Disk IO
- SNMP - Get Mounted Partitions
- SNMP - Interface Statistics

**Data Query [RFC1213 Statistics]**

- IP
- Protocol Traffic
- TCP

**Data Query [SNMP - Get Disk IO]**

Tout les disque, à savoir ce qui finissent par une lettre *ex: sda, sdb ...* sont des disque.
Ceux finissant par des chiffres sont des partitions *ex: sd1, sd2 ...*
On ne graph que les disque pas les partition :
- Host MIB - Disk IO - Bytes per second
- Host MIB - Disk IO - Transactions


**Data Query [SNMP - Get Mounted Partitions]**

Toutes les partitions que possèdent la machine, principalement
- /
- /srv
- /backup
- /var


**Data Query [SNMP - Interface Statistics]**

On graph le traffic, voir les ports up pour les graphs.
- Default - In/Out Bits (64-bit Counters)
- Default - In/Out Errors/Discarded Packets
- Default - In/Out Unicast Packets

Si votre machine utilisent des compteurs différents.
*Exemple : Postgresql, Nginx, php-fpm ...*
Ajouter le template associé et mettre les graphs (en général tous les graphs sont à mettre sur ces différents templates).

Lien du pad BCS http://pad.bcs.cx/p/Procedure_Monitoring

