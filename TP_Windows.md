# TP Windows Serveur 2012:

## Installation d'un serveur version core

Lancez le début d'une instalation classique
![Exemple1](http://portfolio.fpompey.com/images/ESGI/Exemple1-Frame_Relay.png)
Changez la langue qui est actuellement en anglais
(2 images de changements)
Installation via sconfig
- Changement du hostname (un redémarage est requis) (2 images)
- Paramètre réseau
- Si nécéssaire mise à jour (option 6) Redémarage du serveur
- Setup d'un mot de passe pour le compte administrator (net user administrator * )

Installations du ActiveDirectory
    Install-windowsfeature - name AD-Domain-Services -IncludeManagementTools

Installation des services domaines
    Install-windowsfeature DNS -IncludeManagementTools

Création de la forêt Active Directory
  Install-ADDSForest -DomainName pompeyflorian.local -DomainNetBiosName POMPEYFLORIAN
Restart à la fin de l'installation.

Sur l'interface ajouter le serveur qui n'as pas crée le domaine et la forêt et faire un "promote this server"

## Configuration du serveur en tant que Catalogue Global

Il faut se rendre depuis le serveur avec l'interface sur "Sites et services Active Directory"
Dérouler l'arborescense "Sites and services Active Directory\Sites\nom_site\Serveurs" jusqu'à trouver votre serveur.
Sur votre serveur, sur l'option Paramètres NTDS cliquer sur propriétés.

Activer ou désactiver le Catalogue global

## Site de réplication contenant la planification de la réplication avec les controleurs du domaine visibles

## L'OU des controlleurs de domaines (avec les machines visibles)

Dans Active Directory Users ans Computers, nous allons crée une unité organisationnelle 'OU'
Sur votre domaine faites un click droit puis "nouveau\Organisation Unit"
Une fois l'OU Holding crée à la racine du domaine, nous allons crée trois OU (Compta, Marketing, Informatique) dans le groupes Holding. Même opération que tout à l'heure click droit puis "nouveau\Organisation Unit"

## L'arborescence avec les groupes et les utilisateurs crée

Une fois les 3 OU crées, dans l'OU "compta" nous allons crée les groupes de sécurité "assistants" et "chefs comptables"
click droit puis "nouveau\Group"

Effectuer de nouveau la même opération pour crée les groupes "acceuil" et "assistantes" dans l'OU marketing et les groupes "developpeurs" et "techniciens" dans l'OU informatique

Maintenant que tous nos groupes ont été crée nous allons ajouter des utilisateurs.

Nous allons crée 4 utilisateurs, rendez vous dans l'OU ou vous souhaitez crée l'utilisateur puis effectuez un click droit "nouveau\users"
Renseignez les informations nécéssaire, attntion à bien cocher la case pour que le mot de passe n'expire jamais puis finish.

Pour l'affecter à un groupe faites un click droit sur l'utilisateur "Add to a group" et ajouter le au group adéquat

Effectuer la même opération pour les 3 autres utilisateurs.

Nous pouvons toujours modifier ces informations en allant dans les propriétés de l'utilisateur ou du groupes

Nous pouvons également effectuer ces actions depuis le MMC Active Directory Administratice Center

## Les propriétés d'un utilisateur avec le mot de passe n'expirant pas

## Les propriétés d'un groupe de sécurité

## Les membres d'un groupes de sécurité marketing et informatique

## Les 2 consoles MMC utilisateurs et Ordinateurs Active Directory
