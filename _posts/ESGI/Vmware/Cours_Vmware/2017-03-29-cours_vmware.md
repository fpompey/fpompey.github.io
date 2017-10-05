---
layout: page
title:  "Cours Vmware"
teaser: "Cours Vmware réalisé la semaine du 27 Mars 2017"
breadcrumb: false
tags:
    - ESGI
    - vmware
    - Cours
categories:
    - cours_vmware
show_meta: false
---

Système d'exploitation d'un ESXi est un VMkernel. ESXi supérieur à la version 5.1  
Vcenter serveur est une application windows qui permet d'avoir une visibilité sur notre ferme et qui peux disposer de fonctionnalité avancée.    
Appliance Vcenter. Une appliance est un modèle que l'on déploit qui contient toutes les caractéristiques nécéssaire. (Limité à 50VM ou 3 hyperviseur)

*Exemple de question :*

**Quel produit VmWare va permettre de rendre votre infrastructure plus efficace ?**

L'Esxi dispose des allocations de ressources physique pour les ressources virtuelles, il fait le lien entre les deux.    
L'hyper traiding prend le nombre de vCPU disponible x 2, en contrepartie il fonctionnera potetiellement plus lentement selon les ressources.

# Les fichiers de la VM (par coeur)

Une machine virtuelle = des fichiers, un fichier par ressource et un fichier par ressources.  
Les quatres ressources :
  - CPU
  - RAM
  - Réseau
  - Disques

## Disque

VMDK => fichier description disque de la VM. (Il ne contient pas les données)
Flat-vmdk => Contient les données.  

2 types de disques virtuelle :
  - thin (allocation dynamique - plutôt à proscrire)
  - thick (allocation fixe - on peux voir immédiatement l'allocation du disque)

2 modes possibles pour les types:
  - lazy 0 (disque crée rapidement - 2 opération Initialisation du disque puis écriture du disque)
  - eager 0 (disque crée lentement - Initialise tous les secteurs de disques à 0)

## Configuration

Fichier VMX => fichier de onfiguration de la machine.  
Fichier nvram => fichier de Bios fournie par vmware.  
Fichier log => Toutes les allocations

VMSS => etat de la vm en mode suspend
vswp => un espace disque qui sert de mémoire en cas de surcharge de la ram. Généralement la même taille que la ram. Le fichier est crée à l'initialisation de la machine.

## Snapshot

Le snapshot est un différentiel de donnée, il est crée dans fichier différent, ce fichier peux grandir à l'infini il ne faut donc pas le garder trop longtemps.  
Un snapshot sera remove si les modifications veulent être supprimé ou consolider afin de rejouer toutes les actions du snapshot que le disque principal.

# VMWare Tools

Permet de fournir les drivers optimals.
Permet d'arreter proprement une machine.
Fournit les drivers de ballooning.
Meilleure performances graphiques à l'aide du driver (ne dépend que des ressources fournis à la machine au niveau ram et cpu).

# Fonctionnalités du Vcenter (par coeur)

HA => High availability - Plan de reprise d'activité
Redémarre sur un autre hyperviseur.     
Prérequis:

  - 2 hyperviseur
  - License comprenant le HA pour le Vcenter
  - Avoir le Vcenter
  - Licence vcenter comprenant le HA pour l'hyperviseur
  - Avoir un cluster (dans le VDC)
  - Avoir un VDC (virtual Datacenter)
  - Avoir un stockage partagé visible pour tous les Vcenters.
  - Activer le HA

FT => Fault Tolerance - permet d'avoir 0 coupure de service - image fantome de la machine virtuelle sur un autre hyperviseur qui va faire fonctionner en temps réel sur la machine fantome.
Consomme autant de ressources.  
Prérequis:

- Avoir HA
- 2 hyperviseur
- License comprenant le FT pour l'hyperviseur
- Avoir le Vcenter
- Licence vcenter comprenant le FT
- Avoir un VDC (virtual Datacenter)
- Avoir un cluster (dans le VDC)
- Avoir un stockage partagé visible pour tous les Vcenters.
- Le disque doit impérativement être en thick
- Avoir un réseau FT dédié pour les deux hyperviseurs
- Procésseur récent et identiques
- Activer le FT

Vmotion => Deplacement réseau (effectue un routage du flux), déplacement ram utilise swap + snapshot (effectue une image disque sur le stockage sans le déplacer), Déplacement CPU (Même barque de processeurs)  
Prérequis:

- Avoir HA
- 2 hyperviseur
- License comprenant le Vmotion pour l'hyperviseur
- Avoir le Vcenter
- Licence vcenter comprenant le Vmotion
- Avoir un VDC (virtual Datacenter)
- Avoir un cluster (dans le VDC)
- Avoir un stockage partagé visible pour tous les Vcenters.
- Le disque doit impérativement être en thick
- Avoir un réseau Vmotion dédié pour les deux hyperviseurs
- Avoir les mêmes CPU
- Activer option EVC
- Activer le Vmotion

Storage VMotion => Idem que VMotion mais dédié au stockages. Déplacement des fichiers.

 - Avoir un stockage partagé

EVC => Prend le composant le plus bas pour s'adapter avec les autres générations.

DRS => Distributed ressources Scheduler - Réparties la charge entre les différents hyperviseur.
Prérequis:

  - Idem HA
  - Idem Vmotion

DPM => Distributed power management -  Gestion des ressources grâce à DRS, eteint certain hyperviseur en fonction des besoins.
Prérequis:

  - Idem DRS
  - Wake on lan


**PowerCLI vmware:**

se connecter au Vcenter : Connect-VIServer -Server 172.180.0.x

get-vm : affiche les vm sur les ESXi

get-vmhost : Affiche les hosts connecté

get-inventory : Fais un inventaire complet

get-vm - name 'debian Test' | get-vmhost : affiche ou est le host de la vm

Move-VM 'debian test' -destination 172.180.0.x : fait une migration test ver l'ESXi

get-vm -name 'debian test' | get-datastore : affiche la location du datastore de la vm

remove-cluster "Nom_cluster" : supprime un cluster

Remove-Datacenter "NomDataCenter" : Supprime un DC

New-Datacenter "nomDataCenter"
