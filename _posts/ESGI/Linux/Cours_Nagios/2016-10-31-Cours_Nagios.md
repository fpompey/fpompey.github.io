On va parler Nagios et supervision
on va installer nagios
bosser sur l'interface web, mettre des plugins
faire des configs avancées
NRPE
SNMP

nagios peut accepter des infos venant d'autres services et processus grace aux plugins
2 types d'objets surveillés, les hosts (serveurs, routeurs, imprimantes...) et les services
On peut faire des hostgroups

4 états nagios :
- OK              
- Warning       
- Critical      
- Unknown       
L'admin peut ignorer les valeurs et décider des limites pour warning et critical

Plugins
Les plugins vont faire des vérifications selon des limites fixées par nagios, la vérification renvoie un statut
- working
- questionable
- failure
et parfois un texte décrivant l'information

fonctionnalités principales
- les commandes
- les hosts et host groups
- les time periods
- les services
- les contacts et groupes de contacts
- les notifications
- les escalations (suite d'actions si y'a des erreurs)

dépendances
nagios peut définir des dépendances entre les hôtes pour refléter la topologie réelle du réseau
par exemple si un routeur est inaccessible, nagios ne testera pas les machines qui sont dépendantes du routeur
(si on ne l'a pas prévu, tous les hosts et services derrière le routeur feront des notifs)
Ca peut être des dépendances entre hosts ou entre services

Macros
variables qu'on peut insérer dans les définitions des objets
avant d'executer une commande, nagios remplacera les macros par leurs valeurs

planification des downtimes, ça va prendre en compte les dépendances et ne pas spammer les notifs

nagios état soft et état hard
en gros soft c'est temporaire et hard c'est sur
quand un truc plante, ça va d'abord faire des tests pour s'assurer que c'est HS, et une fois que c'est vérifié
(avec les nouveaux intervales de tests), il va dire "ah bah oui c'est bien planté effectivement"
ça permet d'éviter un déclanchement de toutes les notifications si on a seulement un freeze de 2mn



installation de nagios
Compileur C
Librairies de développement standard C
Commandes make/imake
pour utiliser l'interface web: un serveur web capable de gérer les scripts CGI (apache est recommandé)
Beaucoup de plugins sont développés en Perl
Librairies graphiques GD pour gérer les images sur l'interface web + librairies JPEG et PNG
Fichiers de développement openSSL pour les plugins réseau
packages de développement mySQL et PostgreSQL pour pouvoir vérifier les BDD
