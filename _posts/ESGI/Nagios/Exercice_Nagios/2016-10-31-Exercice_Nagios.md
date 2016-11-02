---
layout: page
title:  "Exercice Nagios"
teaser: "Exercice Nagios lors de la semaine du 31 Octobre 2016"
breadcrumb: false
tags:
    - ESGI
    - Nagios
    - Exercice
categories:
    - exercice_nagios
show_meta: false
---

Dans un premier temps nous avons installé les dépendances que nous avions besoin :

    apt-get install gcc make binutils cpp libpq-dev libmysqlclient-dev libssl1.0.0 libssl-dev pkg-config libgd2-xpm-dev libgd-tools perl libperl-dev snmp apache2 libapache2-mod-php5

Puis nous avons crée le répértoire nécéssaire pour mettre en place nagios

    mkdir /usr/src/nagios4

Dans le répértoire créer, nous avons récuppéré les paquets nagios

    cd /usr/src/nagios4/
    wget https://assets.nagios.com/downloads/nagioscore/releases/nagios-4.2.2.tar.gz
    wget https://nagios-plugins.org/download/nagios-plugins-2.1.2.tar.gz

Décompréssé les fichiers

    tar xf nagios-4.2.2.tar.gz
    tar xf nagios-plugins-2.1.2.tar.gz

Crée l'utilisateur nagios et lui donner ses droits

    groupadd nagios
    groupadd nagioscmd  
    useradd -g nagios -G nagioscmd -d /opt/nagios nagios
    usermod -G nagioscmd www-data

Crée les différents répértoires utiles pour nagios et lui affecter les permissions et droits

    mkdir -p /opt/nagios /etc/nagios /var/nagios
    chown nagios:nagios /opt/nagios/ /etc/nagios/ /var/nagios/
    sh configure --prefix=/opt/nagios/ --sysconfdir=/etc/nagios --localstatedir=/var/nagios --libexecdir=/opt/nagios/plugins --with-command-group=nagioscmd

Une fois fait nous avons lancé les installations

    cd /usr/src/nagios4/nagios-4.2.2
    make all
    make install
    make install-init
    make install-commandmode
    make install-config

Même chose dans le dossier plugins-2.1.2

    cd /usr/src/nagios4/nagios-plugins-2.1.2
    make all
    make install
    make install-init
    make install-commandmode
    make install-config

Récupérer les fichiers nécéssaires

    su -c '/opt/nagios/bin/nagios /etc/nagios/nagios.cfg' nagios

Update des fichiers

    make install-init
      update-rc.d nagios defaults

On va modifier le fichier de configuration de nagios dans

    /etc/nagios/nagios.cfg

Commenter tous les cfg_file ou cfg_dir avec un # en début de ligne

Ajouter ensuite à la suite des cfg_dir

    cfg_dir=/etc/nagios/commands
    cfg_dir=/etc/nagios/timeperiods
	  cfg_dir=/etc/nagios/contacts
    cfg_dir=/etc/nagios/contactgroups
    cfg_dir=/etc/nagios/hosts
    cfg_dir=/etc/nagios/hostgroups
    cfg_dir=/etc/nagios/services
    cfg_dir=/etc/nagios/servicegroups

Il faut ensuite crée les différents répertoires déclaré dans le fichier de configuration

    mkdir commands timeperiods contacts contactgroups hosts hostgroups services servicegroups

Pour utiliser les plugins par défaut de nagios il faut copier le fichier de définition de commandes dans le nouveau répértoire

    cp objects/commands.cfg commands/default.cfg

On peux vérifier

    lscommands/

On devrait voir

    default.cfg

Création du premier hosts dans

    /etc/nagios/hosts/localhost.cfg
    define host{
      host_name                 localhost
      alias                     localhost
      address                   127.0.0.1
      check_command             check-host-alive
      check_interval            5
      retry_interval            1
      max_check_attempts        5
      check_period              24x7
      contactgroups             admins
      notification_interval     60
      notification_period       24x7
      notification_options      d,u,r
    }

Création du premier services

    /etc/nagios/services/localhost-www.cfg
    define service{
      host_name                 localhost
      service_description       www
      check_command             check_http
      check_interval            10
      check_period              24x7
      retry_interval            1
      max_check_attempts        3
      contact_groups            admins
      notification_interval     60
      notification_period       24x7
      notification_options      w,c,u,r
    }

Monitorer service ssh

    /etc/nagios/services/localhost-ssh.cfg
    define service{
      host_name                 localhost
      service_description       ssh
      check_command             check_ssh
      check_interval            5
      check_period              24x7
      retry_interval            1
      max_check_attempts        3
      contact_groups            admins
      notification_interval     60
      notification_period       24x7
      notification_options      w,c,u,r
    }

Création timeperiod

    /etc/nagios/timeperiods/timeperiods.cfg
    define timeperiod{
      timeperiod_name 24x7      
      alias                     24 Hours A Day, 7 Days A Week
      sunday                    00:00-24:00
      monday                    00:00-24:00
      tuesday                   00:00-24:00
      wednesday                 00:00-24:00
      thursday                  00:00-24:00
      friday                    00:00-24:00
      saturday                  00:00-24:00
    }

    define timeperiod{
      timeperiod_name workinghours      
      alias                     Normal Work Hours
      sunday                    09:00-17:00
      monday                    09:00-17:00
      tuesday                   09:00-17:00
      wednesday                 09:00-17:00
      thursday                  09:00-17:00
      friday                    09:00-17:00
      saturday                  09:00-17:00
    }

    define timeperiod{
      timeperiod_name weekends      
      alias                     Weekends all daylong
      saturday                  00:00-24:00
      sunday                    00:00-24:00
    }
Création d'un Contact

    /etc/nagios/contacts/contacts.cfg
    define contact{
      contact_name                    fpompey
      alias                           Florian POMPEY
      email                           florian.pompey@gmail.com
      contactgroups                   admins,nagiosadmin
      host_notification_period        24x7
      service_notification_period     24x7
      host_notification_options       d,u,r
      service_notification_options    w,u,c,r
      host_notification_commands      notify-host-by-email   
      service_notification_commands   notify-service-by-email
    }

Création d'un groups de contact

    /etc/nagios/contactgroups/admins.cfg
    define contactgroup{
      contactgroup_name         admins
      alias                     Administrateur système
    }

    define contactgroup{
      contactgroup_name         nagiosadmin
      alias                     Administrateur nagios
    }

Reload de la conf pour vérifier les éventuelles erreurs

    /opt/nagios/bin/nagios -v /etc/nagios/nagios.cfg
