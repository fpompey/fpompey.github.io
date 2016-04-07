---
layout: page
title:  "Procédure Installation Linux"
teaser: "Cette procédure à pour but d'aider lors d'une installation pour les machines virtuelles sur Ubuntu"
breadcrumb: true
tags:
    - procedure
    - vm
    - ubuntu
categories:
    - procedure
---

Cette procédure a été réalisée pour Ubuntu.

Pour commencer connecter-vous à ESX à partir de vSphère client

Une fois connectée crée une machine virtuelle :

![alt text](https://fpompey.github.io/images/Installation_Linux/image001.png)

### Créer la Vm en suivant les étapes: ###

Configuration typique

Renommer la VM (essayer de respecter la même syntaxe pour votre réseau).

Choisissez votre espace de stockage :

![alt text](https://fpompey.github.io/images/Installation_Linux/image002.png)

Choisissez votre système d'exploitation :

Pour notre cas *Ubuntu 64 bits*

![alt text](https://fpompey.github.io/images/Installation_Linux/image003.png)

Laisser par défaut le réseau :

![alt text](https://fpompey.github.io/images/Installation_Linux/image004.png)

Choisissez votre taille de disque (garder suffisamment d'espace pour installer le serveur).

Pour notre cas *7GB* seront suffisant.

![alt text](https://fpompey.github.io/images/Installation_Linux/image005.png)

Finaliser l’installation en appuyant sur *Terminer*

Une fois la VM créé activer-la.

Faites un clic droit sur votre nom de VM et "ouvrir console"

### Maintenant il suffit d'ajouter l'ISO du serveur que l'on souhaite installer: ###

![alt text](https://fpompey.github.io/images/Installation_Linux/image006.png)

Dans notre cas *Ubuntu 14.04 serveur 64bits*

Une fois l'ISO mise allée sur Vm :

![alt text](https://fpompey.github.io/images/Installation_Linux/image007.png)

Commencer la procédure d’installation du serveur, certaines options pourront différer

-   Choix langue : Défini par le client (anglais permet de mieux identifier les rapports d’erreurs)

-   Choix du nom machine

-   Choix identifiant (qui seront supprimés par la suite)

-   Choix mot de passe (idem)

-   Choix partitionnement disque Manuel

### Nous allons créer le partitionnement de notre VM ###


 - Choisir le disque dur principal afin de commencer le partitionnement et crée votre volume Groupe qui sera appelé main, n’oubliez pas de le séléctionnez:

![alt text](https://fpompey.github.io/images/Installation_Linux/image008.png)


 - Crée ensuite 2 volume logique, 1 swap (non obligatoire dépend si la ram est suffisante) de 1G et un root de 5G (la encore dépend du besoin de votre VM).

Attention selon votre installation votre partitionnement pourra être un peu différent au niveau du partitionnement, demander le nombre, le nom précis des volumes logiques ainsi que la taille nécessaires avant la configuration.

![alt text](https://fpompey.github.io/images/Installation_Linux/image009.png)

Pour root préciser :

![alt text](https://fpompey.github.io/images/Installation_Linux/image010.png)

Monter la partition root sur :

![alt text](https://fpompey.github.io/images/Installation_Linux/image011.png)

Votre partitionnement root devrait ressembler à ceci :

![alt text](https://fpompey.github.io/images/Installation_Linux/image012.png)

La configuration du *swap* doit être :

![alt text](https://fpompey.github.io/images/Installation_Linux/image013.png)

Vos volumes crée devrait ressembler à :

![alt text](https://fpompey.github.io/images/Installation_Linux/image014.png)

Choisissez votre choix de mise à jour (non automatique est conseillé pour éviter tout problème)

Installez les programmes désirés, pour notre cas nous allons rajouter *OpenSSH server* :

![alt text](https://fpompey.github.io/images/Installation_Linux/image015.png)

Installer *GRUB*

Une fois l’installation terminé, connecter vous avec les identifiants précédemment crée.

Félicitation vous êtes connecter à votre VM et pouvez commencer à l'utiliser.

Connectez-vous en root avec 

    sudo -i (mot de passe de la session)

Faire un *apt-get update* puis un *apt-get upgrade* afin de mettre tout à jour.

Pour la suite de la procédure, il est conseillé de se connecter via *ssh* à votre machine.

Pour connaitre votre ip faire un if config et regarder l’adresse inet addr :

![alt text](https://fpompey.github.io/images/Installation_Linux/image016.png)

Dans notre cas 10.0.16.164

Soit ssh fpompey@10.0.16.164

## Installer les différents modules nécessaires: ##

    apt-get install zsh ntp binutils bsd-mailx bsdtar dstat ethtool htop ifstat iftop iotop ipcalc ngrep nmap numactl pbzip2 pwgen snmp snmpd sysstat traceroute tree unzip vlan whois ssh postfix unzip libnet-ntp-perl libwww-perl

Laisser l’installation de base pour *postfix* appuyez sur entrée, si cela concerne une VM ajouter 

    apt-get install open-vm-tools

Configurer le *zsh*, pour cela utiliser celui que vous possedez. Récupérer le et ajouter le dans */etc/zsh* à la place du fichiers texte zshrc.

Une fois ajouté faite un *chsh* et changer le nom en */bin/zsh*

![alt text](https://fpompey.github.io/images/Installation_Linux/image017.png)

Déconnecter vous et reconnecter vous et le zsh devraient être correctement configuré :

![alt text](https://fpompey.github.io/images/Installation_Linux/image018.png)

### Pour installer la BCS-probe ###

Récupérer BCS-probe

Dpkg –i vers le .deb que l’on a rajouté, si une dépendance existe faire *apt-get install -f*

Test avec 

    /opt/bcs-probe/bcs-probe --diag

Tapez la commande suivante

    vi /etc/ssh/sshd_config
    
Localisez la ligne *PermitRootLogin* et remplacez « no » par « yes » 

Tapez *:wq* pour enregistrer (write) et sortir (quit) de vi

Exécutez ensuite un 

    *service sshd restart* 
    
pour redémarrer le service SSH

Effectuer un *passwd* pour changer le mot de passe root et renseigner le afin de ne pas l’oublier.

Supprimer l’utilisateur précédemment utilisé avec *deluser [nom]*

### Pour mettre une communauté ###

    vim /etc/snmp/snmpd.conf

Afficher les lignes avec :set nu garder la dernière ligne

Pour supprimer plusieurs ligne, faite un 

    :\[Première_ligne\],\[Dernière_ligne\]d

Faite un

    rocommunity [nom]

### Pour fixer une ip statique : ###

Dans */etc/network/interface* modifier :

    iface eth0 inet static
    address x.x.x.x
    netmask y.y.y.y
    gateway x.x.x.z

Faite un 

    apt-get remove resolvconf

Aller dans */etc/resolv.conf*

Et mettre 

    nameserver 8.8.8.8
