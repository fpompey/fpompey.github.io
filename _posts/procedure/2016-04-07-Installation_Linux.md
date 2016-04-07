Cette procédure a été réalisée pour Ubuntu.

Pour commencer connecter-vous à ESX à partir de vSphère client

Une fois connectée crée une machine virtuelle :

<img src="./media/image1.png" width="482" height="206" />

Créer la Vm en suivant les étapes :

Configuration typique

Renommer la VM (essayer de respecter la même syntaxe pour votre réseau).

Choisissez votre espace de stockage :

<img src="./media/image2.png" width="460" height="168" />

Choisissez votre système d'exploitation :

Pour notre cas Ubuntu 64 bits

<img src="./media/image3.png" width="445" height="300" />

Laisser par défaut le réseau :

<img src="./media/image4.png" width="402" height="241" />

Choisissez votre taille de disque (garder suffisamment d'espace pour installer le serveur).

Pour notre cas 7GB seront suffisant.

<img src="./media/image5.png" width="514" height="210" />

Finaliser l’installation en appuyant sur Terminer

Une fois la VM créé activer-la.

Faites un clic droit sur votre nom de VM et "ouvrir console"

Maintenant il suffit d'ajouter l'ISO du serveur que l'on souhaite installer :

<img src="./media/image6.png" width="642" height="146" />

Sur le réseau Commun/Linux/ISO/ \[Nom\_Sys\_Exploitation\]

Dans notre cas Ubuntu 14.04 serveur 64bits

Une fois l'ISO mise allée sur Vm :

<img src="./media/image7.png" width="436" height="162" />

Commencer la procédure d’installation du serveur, certaines options pourront différer

-   Choix langue : Défini par le client (anglais permet de mieux identifier les rapports d’erreurs)

-   Choix du nom machine

-   Choix identifiant (qui seront supprimés par la suite)

-   Choix mot\_de\_passe (idem)

-   Choix partitionnement disque Manuel :

Nous allons créer le partitionnement de notre VM.

1) Choisir le disque dur principal afin de commencer le partitionnement et crée votre volume Groupe qui sera appelé main, n’oubliez pas de le séléctionnez:

<img src="./media/image8.png" width="494" height="219" />

Crée ensuite 2 volume logique, 1 swap (non obligatoire dépend si la ram est suffisante) de 1G et un root de 5G (la encore dépend du besoin de votre VM).

Attention selon votre installation votre partitionnement pourra être un peu différent au niveau du partitionnement, demander le nombre, le nom précis des volumes logiques ainsi que la taille nécessaires avant la configuration.

<img src="./media/image9.png" width="434" height="216" />

Pour root préciser :

<img src="./media/image10.png" width="198" height="182" />

Monter la partition root sur :

<img src="./media/image11.png" width="291" height="194" />

Votre partitionnement root devrait ressembler à ceci :

<img src="./media/image12.png" width="478" height="222" />

La configuration du swap doit être :

<img src="./media/image13.png" width="198" height="184" />

Vos volumes crée devrait ressembler à :

<img src="./media/image14.png" width="439" height="188" />

Choisissez votre choix de mise à jour (non automatique est conseillé pour éviter tout problème)

Installez les programmes désirés, pour notre cas nous allons rajouter OpenSSH server :

<img src="./media/image15.png" width="479" height="222" />

Installer GRUB

Une fois l’installation terminé, connecter vous avec les identifiants précédemment crée.

Félicitation vous êtes connecter à votre VM et pouvez commencer à l'utiliser.

Connectez-vous en root avec sudo -i (mot de passe de la session)

Faire un apt-get update puis un apt-get upgrade afin de mettre tout à jour.

Pour la suite de la procédure, il est conseillé de se connecter via ssh à votre machine.

Pour connaitre votre ip faire un if config et regarder l’adresse inet addr :

<img src="./media/image16.png" width="469" height="234" />

Dans notre cas 10.0.16.164

Soit ssh fpompey@10.0.16.164

II) Installer les différents modules nécessaires :

apt-get install zsh ntp binutils bsd-mailx bsdtar dstat ethtool htop ifstat iftop iotop ipcalc ngrep nmap numactl pbzip2 pwgen snmp snmpd sysstat traceroute tree unzip vlan whois ssh postfix unzip libnet-ntp-perl libwww-perl

Laisser l’installation de base pour postfix appuyez sur entrée, si VM : open-vm-tools.

Configurer le zsh, pour cela utiliser celui de M6 par exemple. Récupérer le et ajouter le dans /etc/zsh à la place du fichiers texte zshrc.

Une fois ajouté faite un chsh et changer le nom en /bin/zsh :

<img src="./media/image17.png" width="448" height="65" />

Déconnecter vous et reconnecter vous et le zsh devraient être correctement configuré :

<img src="./media/image18.png" width="435" height="156" />

Pour installer la BCS-probe.

Récupérer BCS-probe dans Exploitation/\_outil\_BCS/OUTIL - BCS-Probe - Sonde SNMP pour Linux/bcs-probe/\[Dernière\_Version\_de\_la\_BCS-PROBE\]

Dpkg –i vers le .deb que l’on a rajouté, si une dépendance existe faire apt-get install -f.

Test avec /opt/bcs-probe/bcs-probe --diag

Tapez la commande suivante: vi /etc/ssh/sshd\_config

Localisez la ligne PermitRootLogin et remplacez « no » par « yes«

Tapez :wq pour enregistrer (write) et sortir (quit) de vi (pas toujours évident pour les débutants )

Exécutez ensuite un service sshd restart pour redémarrer le service SSH

Effectuer un passwd pour changer le mot de passe root et renseigner le afin de ne pas l’oublier.

Supprimer l’utilisateur précédemment utilisé avec deluser \[nom\]

Pour mettre une community aller dans vim /etc/snmp/snmpd.conf odaelium

Afficher les lignes avec :set nu garder la dernière ligne

Pour supprimer plusieurs ligne, faite un :\[Première\_ligne\],\[Dernière\_ligne\]d

Faite un rocommunity \[nom\]

Pour fixer une ip statique :

Dans /etc/network/interface modifier :

iface eth0 inet static

address x.x.x.x

netmask y.y.y.y

gateway x.x.x.z

Faite un apt-get remove resolvconf

Aller dans /etc/resolv.conf

Et mettre nameserver 8.8.8.8
