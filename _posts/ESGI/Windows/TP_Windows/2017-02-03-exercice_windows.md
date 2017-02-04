---
layout: page
title:  "TP Windows Server 2012"
teaser: "TP sur Windows server 2012 & Active directory réalisé le vendredi 03 Février 2016"
breadcrumb: false
tags:
    - ESGI
    - windows
    - Exercice
categories:
    - exercice_windows
show_meta: false
---

<!-- TOC depthFrom:1 depthTo:6 withLinks:1 updateOnSave:1 orderedList:0 -->

- [TP Windows Serveur 2012:](#tp-windows-serveur-2012)
	- [Installation d'un serveur version core](#installation-dun-serveur-version-core)
		- [Changement du hostname](#changement-du-hostname)
		- [Paramètre réseau](#paramtre-rseau)
		- [Setup d'un mot de passe pour le compte administrator](#setup-dun-mot-de-passe-pour-le-compte-administrator)
		- [Active Directory core](#active-directory-core)
	- [Installation d'un serveur standard](#installation-dun-serveur-standard)
	- [Ajout d'un serveur en tant que contrôleur de domaine dans le domaine existant](#ajout-dun-serveur-en-tant-que-contrleur-de-domaine-dans-le-domaine-existant)
		- [Version Core](#version-core)
		- [Version Standard](#version-standard)
	- [Configuration du serveur en tant que Catalogue Global](#configuration-du-serveur-en-tant-que-catalogue-global)
	- [Site de réplication](#site-de-rplication)
	- [Création d'un OU](#cration-dun-ou)
	- [Création des groupes de sécurités](#cration-des-groupes-de-scurits)
	- [Créations des utilisateurs](#crations-des-utilisateurs)

<!-- /TOC -->

# TP Windows Serveur 2012:

Dans ce TP nous allons mettre en place deux serveurs Windows 2012 R2 de deux façons.
  - Installation en version core nommé nomprenom01
  - Installation en version Standard nommé nomprenom02

## Installation d'un serveur version core

Lancez le début d'une instalation classique en anglais.  
Attention à bien mettre votre clavier en azerty si nécéssaire, cela pourra être changer plus tard en cas d'oubli.  
![Installation de base](http://portfolio.fpompey.com/images/ESGI/TP_Windows_Server/Install_base_1.png)

L'installation se lance.  
![Installation de base](http://portfolio.fpompey.com/images/ESGI/TP_Windows_Server/Install_base_2.png)

Une fois sur votre terminal de commande passez en powershell pour commencer la configuration de base.

    powershell

![Changement de langue](http://portfolio.fpompey.com/images/ESGI/TP_Windows_Server/Changement_Langue_1.png)

Si vous avez oubliez de passer votre clavier en qwerty vous pouvez effectuer la commande

    Set-WinUserLanguageList fr-fr

![Changement de langue](http://portfolio.fpompey.com/images/ESGI/TP_Windows_Server/Changement_Langue_2.png)

Si vous avez besoin de vérifier la commande est

    Get-WinUserLanguageList

![Changement de langue](http://portfolio.fpompey.com/images/ESGI/TP_Windows_Server/Changement_Langue_3.png)  

Pour cette installation nous allons passer via sconfig, toutes les modifications que nous allons faire peuvent également se faire manuellement.

    sconfig

Nous allons effectuer plusieurs changement :

### Changement du hostname

Option **2** (un redémarage est requis)

![Changement de Hostname](http://portfolio.fpompey.com/images/ESGI/TP_Windows_Server/Changement_Hostname_1.png)

![Changement de Hostname](http://portfolio.fpompey.com/images/ESGI/TP_Windows_Server/Changement_Hostname_2.png)

![Changement de Hostname](http://portfolio.fpompey.com/images/ESGI/TP_Windows_Server/Changement_Hostname_3.png)

### Paramètre réseau

Option **8**

Pour ce TP nous allons avoir besoin de passer en **IP fixe**, vous devriez avoir la liste de toutes vos connexions ethernet sur la machine.

![Changement de Network](http://portfolio.fpompey.com/images/ESGI/TP_Windows_Server/Changment_Network_Settings_1.png)

Dans notre cas il n'y en as qu'une seul, l'index **10**.

![Changement de Network](http://portfolio.fpompey.com/images/ESGI/TP_Windows_Server/Changment_Network_Settings_2.png)

Nous allons ensuite mettre enplace notre IP statique option **1** et **S**

![Changement de Network](http://portfolio.fpompey.com/images/ESGI/TP_Windows_Server/Changment_Network_Settings_3.png)

Puis mettre en place les DNS option **2**

![Changement de Network](http://portfolio.fpompey.com/images/ESGI/TP_Windows_Server/Changment_Network_Settings_4.png)

Une fois que tout est bien configuré, nous pouvons vérifier nos informations et sortir avec l'option **4**

![Changement de Network](http://portfolio.fpompey.com/images/ESGI/TP_Windows_Server/Changment_Network_Settings_5.png)

Une fois toutes les modifications effectués nous pouvons sortir de **sconfig** option **15**.

![Installation de base](http://portfolio.fpompey.com/images/ESGI/TP_Windows_Server/Install_base_3.png)  

On peut faire un test de connection pour vérifier que l'accès Internet et les DNS fonctionne correctement.

![Installation de base](http://portfolio.fpompey.com/images/ESGI/TP_Windows_Server/Install_base_4.png)

Pour vérifier ses DNS on peux également effectuer la commande

    Get-NetIPConfiguration

![Installation de base](http://portfolio.fpompey.com/images/ESGI/TP_Windows_Server/Install_base_5.png)

Si on souhaite le changer il faut effectuer la commande

    Set-DNS-ClientServerAddress -interfaceindex 12 -ServerAddresses[*ip*]

![Installation de base](http://portfolio.fpompey.com/images/ESGI/TP_Windows_Server/Install_base_6.png)

### Setup d'un mot de passe pour le compte administrator

Une fois les paramètres réseaux nous allons mettre un mot de passe au compte administrator qui nous sera nécéssaire pour la partie avec Active Directory.

    net user administrator *

![Changement de mot de passe](http://portfolio.fpompey.com/images/ESGI/TP_Windows_Server/Changement_mdp_administrator.png)

L'installation de base sur Windows Server 2012 Core est terminé pour pouvoir effectuer la partie sur Active Directory.

![Installation de base](http://portfolio.fpompey.com/images/ESGI/TP_Windows_Server/Install_base_7.png)

### Active Directory core

Dans notre situation le serveur standard n'est pas encore configuré, nous allons donc crée la partie avec Active Directory.

Nous installons le rôle serveur Active Directory Domain Services :

    Install-windowsfeature - name AD-Domain-Services -IncludeManagementTools

![Installation Active Directory](http://portfolio.fpompey.com/images/ESGI/TP_Windows_Server/Install_Active_Directory_1.png)

Nous installons le rôle serveur DNS

    Install-windowsfeature DNS -IncludeManagementTools

![Installation Active Directory](http://portfolio.fpompey.com/images/ESGI/TP_Windows_Server/Install_Active_Directory_2.png)

Création de la forêt avec le NetBiosName

    Install-ADDSForest -DomainName pompeyflorian.local -DomainNetBiosName POMPEYFLORIAN

Restart à la fin de l'installation.


## Installation d'un serveur standard

Il faut effectuer le même type d'installation qu'effectué plus haut mais en version standard.  
Une fois sur le serveur vous pouvez lancer le terminal

    cmd

Ou bien effectuez les modification depuis l'interface graphique.  
Tout en bas à droite *Open Network and Sharing Center\Change adaptater ettings\[carte_ethernet]\Propriété\IPv4*  
Modifiez les informations pour mettre en place une IPstatique ainsi que les DNS.

*Dans mon cas nous allons configurer le serveur pompeyflorian02 comme rejoignant un domaine déjà existant sinon il suffit de suivre le tuto [içi](http://www.oameri.com/installer-un-controleur-de-domaine-active-directory-sous-windows-serveur-2012/) pour en crée un.*

**Attention si il s'agit d'une création de domaine avec la forêt et le NetBIOS, les DNS doivent être l'IP de la machine elle même sinon il faut que les DNS soit celle de la machine source**, c'est à dire celle qui rejoint le domaine doit avoir les DNS ce la machine qui as crée l'AD, il faudra donc effectuer des modifications selon si vous avez crée depuis la machine Core ou depuis la machine avec l'interface visuelle.

![Installation Serveur Standard](http://portfolio.fpompey.com/images/ESGI/TP_Windows_Server/Configuration_IP_Standard(_1.png)

Vous pouvez vérifier vos information via votre terminal

    ipconfig /all

![Installation Serveur Standard](http://portfolio.fpompey.com/images/ESGI/TP_Windows_Server/Configuration_IP_Standard_2.png)

Vous pouvez également vérifier si vous arrivez bien à joindre votre domaine crée précédemment (depuis l'interface gui ou depuis le core)

![Installation Serveur Standard](http://portfolio.fpompey.com/images/ESGI/TP_Windows_Server/Configuration_IP_Standard_3.png)

Maintenant que la jonction est possible entre les deux serveurs nous allons faire rejoindre le second serveur au domaine.

## Ajout d'un serveur en tant que contrôleur de domaine dans le domaine existant

### Version Core

Nous installons le rôle serveur Active Directory Domain Services :

    Install-windowsfeature - name AD-Domain-Services -IncludeManagementTools

![Installation Active Directory Core](http://portfolio.fpompey.com/images/ESGI/TP_Windows_Server/Install_Active_Directory_1.png)

Nous installons le rôle serveur DNS

    Install-windowsfeature DNS -IncludeManagementTools

![Installation Active Directory Core](http://portfolio.fpompey.com/images/ESGI/TP_Windows_Server/Install_Active_Directory_2.png)

Install-ADDSDomainController -DomainName pompeyflorian.local  
Il faudra saisir un mot de passe et valider, un redémarage sera requis.

### Version Standard

Nous allons ajouter le domaine contrôleur à un domaine existant.

![Installation Active Directory Standard](http://portfolio.fpompey.com/images/ESGI/TP_Windows_Server/Install_Active_Directory_Standard_1.png)

Configuration du serveur en tant que Catalogue Global sur le même site crée précédemment, le mot de passe DSRM est à mettre de coté en cas de panne Active Directory.

![Installation Active Directory Standard](http://portfolio.fpompey.com/images/ESGI/TP_Windows_Server/Install_Active_Directory_Standard_2.png)

Ignorez l'avertissement jaune.

![Installation Active Directory Standard](http://portfolio.fpompey.com/images/ESGI/TP_Windows_Server/Install_Active_Directory_Standard_3.png)

Associez la réplication à un second serveur Active Directory

![Installation Active Directory Standard](http://portfolio.fpompey.com/images/ESGI/TP_Windows_Server/Install_Active_Directory_Standard_4.png)

Laissez les chemins par défaut

![Installation Active Directory Standard](http://portfolio.fpompey.com/images/ESGI/TP_Windows_Server/Install_Active_Directory_Standard_5.png)

Compte rendu global de vos actions

![Installation Active Directory Standard](http://portfolio.fpompey.com/images/ESGI/TP_Windows_Server/Install_Active_Directory_Standard_6.png)

Lancez l'installation

![Installation Active Directory Standard](http://portfolio.fpompey.com/images/ESGI/TP_Windows_Server/Install_Active_Directory_Standard_7.png)

Le serveur va ensuite redémarrez.  
Vos deux serveurs sont tous les deux controlleurs de domaine.

![Jonction Active Directory](http://portfolio.fpompey.com/images/ESGI/TP_Windows_Server/Jonction_Active_Directory.png)


## Configuration du serveur en tant que Catalogue Global

Il faut se rendre depuis le serveur avec l'interface visuelle sur **Active Directory Sites and services**
Dérouler l'arborescense *Sites and services Active Directory\Sites\nom_site\Serveurs* jusqu'à trouver votre serveur.
Sur votre serveur, sur l'option Paramètres NTDS cliquer sur propriétés.

Activer ou désactiver le Catalogue global.

![Catalogue Global](http://portfolio.fpompey.com/images/ESGI/TP_Windows_Server/Configuration_Catalogue_global_1.png)

![Catalogue Global](http://portfolio.fpompey.com/images/ESGI/TP_Windows_Server/Configuration_Catalogue_global_2.png)

## Site de réplication

Par défaut les liens de connexions intra-sites portent le nom *automatically generated*, un seul site *Default-First-Site-Name* et un lien inter site *DefaultIPSiteLink*.  
Dans notre cas nous disposons de deux controlleurs de domaines sur un même site, nous allons donc en crée un second pour en définir un comme master et le second comme Slave.
La réplication intersites va s'effectuer ou via *IP* ou via *SMTP*, dans notre cas nous allons choisir via **IP**

Il faut se rendre depuis le serveur avec l'interface visuelle sur **Active Directory Sites and services**

Dans un premier temps, nous allons renommer le site par défaut avec le nom de son choix, pour ma part il s'appellera **Master** pour le serveur Core.  
Click droit sur *Default-First-Site-Name* et rename.

    Active Directory Sites and Services[nom_domaine_controller]\Sites\Default-First-Site-Name

Pour le second nous allons le crée et il s'appellera **Slave**
Click droit sur *Site* et **New\Site**

    Active Directory Sites and Services[nom_domaine_controller]\Sites\New\Site

Nous pouvons maintenant déplacer un des serveurs sur le site précédemment crée  
Click droit sur *[nom_serveur02]* et **Move** vers **Slave**

    Active Directory Sites and Services[nom_domaine_controller]\Sites\Master\Servers\[nom_serveur02]\Move\Slave

Une fois que le serveur se trouve bien sur le second site nous allons activer la réplication via IP  
Click droit sur *[nom_serveur01]* et **Proprietes**, ajouter IP puis même chose sur *[nom_serveur02]*

    Active Directory Sites and Services[nom_domaine_controller]\Sites\Master\[nom_serveur]\Servers\Proprietes

![Site Réplication](http://portfolio.fpompey.com/images/ESGI/TP_Windows_Server/Site_réplication_1.png)

Après avoir crée les sites nous allons crée les sous_réseaux
Click droit sur *subnet* **New Subnet**, il faut saisir la plage d'adresse et le masque dans notre cas 192.168.50.0/24

    Active Directory Sites and Services[nom_domaine_controller]\Sites\Subnet\New Subnet

Puisque nous avons choisi d'effectuer la réplication via l'IP, nous allons devoir modifier **DEFAULTIPSITELINK**  
Click droit sur *DEFAULTIPSITELINK* dans Inter-site Transport\IP *Proprietes*

    Active Directory Sites and Services[nom_domaine_controller]\Sites\Inter-site Transport\IP\DEFAULTIPSITELINK\Proprietes

![Site Réplication](http://portfolio.fpompey.com/images/ESGI/TP_Windows_Server/Site_réplication_2.png)

Nous pouvons constater que nos deux sites se trouvent bien dans le même lien et nous pouvons modifier la planification.  
Dans notre cas je vais définir la planification de la réplication toutess les heures sauf le mercredi et le samedi.

![Site Réplication](http://portfolio.fpompey.com/images/ESGI/TP_Windows_Server/Site_réplication_3.png)

Nous pouvons ensuite vérifier notre réplication en la lançant manuellement sur le second site, dans **NTDS Settings** et faire **Replicate Configurations to the Selected DS**

Pour vérifier que tout c'est bien déroulé, nous pouvons vérifier en ligne de commande

    repadmin /Showrepl

![Site Réplication](http://portfolio.fpompey.com/images/ESGI/TP_Windows_Server/Site_réplication_4.png)

![Site Réplication](http://portfolio.fpompey.com/images/ESGI/TP_Windows_Server/Site_réplication_5.png)


## Création d'un OU

Dans Active Directory Users ans Computers, nous allons crée une unité organisationnelle 'OU'
Sur notre domaine effectuez un click droit puis **nouveau\Organisation Unit**

![Création OU](http://portfolio.fpompey.com/images/ESGI/TP_Windows_Server/Création_OU_1.png)
![Création OU](http://portfolio.fpompey.com/images/ESGI/TP_Windows_Server/Création_OU_2.png)

Une fois l'OU **Holding** crée à la racine du domaine, nous allons crée trois OU **Compta, Marketing, Informatique** dans l'OU Holding.  
Même opération que tout à l'heure click droit puis **nouveau\Organisation Unit**

![Création OU](http://portfolio.fpompey.com/images/ESGI/TP_Windows_Server/Création_OU_3.png)
![Création OU](http://portfolio.fpompey.com/images/ESGI/TP_Windows_Server/Création_OU_4.png)
![Création OU](http://portfolio.fpompey.com/images/ESGI/TP_Windows_Server/Création_OU_5.png)

## Création des groupes de sécurités

Une fois les *OU* crées, dans **compta** nous allons crée les groupes de sécurité **assistants** et **chefs comptables**  
Click droit puis **nouveau\Group**

![Création OU](http://portfolio.fpompey.com/images/ESGI/TP_Windows_Server/Création_OU_6.png)
![Création OU](http://portfolio.fpompey.com/images/ESGI/TP_Windows_Server/Création_OU_7.png)

Effectuer de nouveau la même opération pour crée les groupes **acceuil** et **assistantes** dans l'OU *marketing* et les groupes **developpeurs** et **techniciens** dans l'OU *informatique*  

![Création OU](http://portfolio.fpompey.com/images/ESGI/TP_Windows_Server/Création_OU_8.png)
![Création OU](http://portfolio.fpompey.com/images/ESGI/TP_Windows_Server/Création_OU_9.png)
![Création OU](http://portfolio.fpompey.com/images/ESGI/TP_Windows_Server/Création_OU_10.png)
![Création OU](http://portfolio.fpompey.com/images/ESGI/TP_Windows_Server/Création_OU_11.png)

## Créations des utilisateurs

Maintenant que tous nos groupes ont été crée nous allons ajouter des utilisateurs.  
Nous allons crée quatres utilisateurs, il faut se rendre dans l'OU ou l'on souhaite crée l'utilisateur puis effectuez un click droit **nouveau\users**
Renseignez les informations nécéssaire, attention à bien cocher la case pour que le **mot de passe n'expire jamais** puis finish.

Utilisateurs Julien DROUET :

![Création OU](http://portfolio.fpompey.com/images/ESGI/TP_Windows_Server/Création_OU_12.png)
![Création OU](http://portfolio.fpompey.com/images/ESGI/TP_Windows_Server/Création_OU_13.png)
![Création OU](http://portfolio.fpompey.com/images/ESGI/TP_Windows_Server/Création_OU_14.png)

Utilisateur Jessica MOTAF :
![Création OU](http://portfolio.fpompey.com/images/ESGI/TP_Windows_Server/Création_OU_15.png)
![Création OU](http://portfolio.fpompey.com/images/ESGI/TP_Windows_Server/Création_OU_16.png)
![Création OU](http://portfolio.fpompey.com/images/ESGI/TP_Windows_Server/Création_OU_17.png)

Utilisateur Jean-Philippe PIAGOT:
![Création OU](http://portfolio.fpompey.com/images/ESGI/TP_Windows_Server/Création_OU_18.png)
![Création OU](http://portfolio.fpompey.com/images/ESGI/TP_Windows_Server/Création_OU_19.png)
![Création OU](http://portfolio.fpompey.com/images/ESGI/TP_Windows_Server/Création_OU_20.png)

Utilisateur Marie-Claire CUBILLE
![Création OU](http://portfolio.fpompey.com/images/ESGI/TP_Windows_Server/Création_OU_21.png)
![Création OU](http://portfolio.fpompey.com/images/ESGI/TP_Windows_Server/Création_OU_22.png)
![Création OU](http://portfolio.fpompey.com/images/ESGI/TP_Windows_Server/Création_OU_23.png)

Pour l'affecter à un groupe faites un click droit sur l'utilisateur **Add to a group** et ajouter le au groupe adéquat

![Création OU](http://portfolio.fpompey.com/images/ESGI/TP_Windows_Server/Création_OU_24.png)

Un message devrait vous valider l'opération

![Création OU](http://portfolio.fpompey.com/images/ESGI/TP_Windows_Server/Création_OU_25.png)

Nous pouvons toujours modifier ces informations en allant dans les *Proprietes* de **l'utilisateur** ou du **groupes**

Onglet **General** pour les informations comme le nom en cas d'erreur orthographique.

![Création OU](http://portfolio.fpompey.com/images/ESGI/TP_Windows_Server/Création_OU_26.png)

Onglet **Member of** pour ajouter ou retirer d'un *groupe*

![Création OU](http://portfolio.fpompey.com/images/ESGI/TP_Windows_Server/Création_OU_27.png)

Onglet **Account** pour modifier le mot de passe ou la période de validité.

![Création OU](http://portfolio.fpompey.com/images/ESGI/TP_Windows_Server/Création_OU_28.png)

Onglet **General** pour les informations global sur le *groupe*

![Création OU](http://portfolio.fpompey.com/images/ESGI/TP_Windows_Server/Création_OU_29.png)

Onglet **Member of** pour voir les utilisateurs présent dans le groupe

![Création OU](http://portfolio.fpompey.com/images/ESGI/TP_Windows_Server/Création_OU_30.png)

Nous avons désormais fini de crée les utilisateurs dans les **OU** et **groupes** pour nos deux contrôleurs de domaines

![Création OU](http://portfolio.fpompey.com/images/ESGI/TP_Windows_Server/Création_OU_31.png)

L'arborescence du groupe marketing

![Création OU](http://portfolio.fpompey.com/images/ESGI/TP_Windows_Server/Création_OU_32.png)

L'arborescence du groupe Informatique

![Création OU](http://portfolio.fpompey.com/images/ESGI/TP_Windows_Server/Création_OU_33.png)

Nous pouvons également effectuer ces actions et modification depuis le MMC **Active Directory Administratice Center**

Arborescence du groupe Informatique

![Création OU](http://portfolio.fpompey.com/images/ESGI/TP_Windows_Server/Création_OU_34.png)

Pour modifier les information d'un utilisateur click droit sur lui et avoir des informations tel que :

Modification d'un utilisateur

![Création OU](http://portfolio.fpompey.com/images/ESGI/TP_Windows_Server/Création_OU_35.png)

Plus bas vous pouvez également modifier à quel groupe est membre l'utilisateur
![Création OU](http://portfolio.fpompey.com/images/ESGI/TP_Windows_Server/Création_OU_36.png)

Modification d'un groupe

![Création OU](http://portfolio.fpompey.com/images/ESGI/TP_Windows_Server/Création_OU_37.png)

Avec les membres présents dans le groupe

![Création OU](http://portfolio.fpompey.com/images/ESGI/TP_Windows_Server/Création_OU_38.png)

Nous avons terminé la partie OU, utilisateur, groupes et les deux MMC possible à utiliser.  
Nos Serveurs Windows 2012 R2 sont maintenant fonctionnelles et disposent d'un Active Directory configuré prêt à être utilisé.
