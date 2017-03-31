---
layout: page
title:  "Exercices Langage de scripting Shell et Python"
teaser: "Exercices Langage de scripting Shell et Python lors de la semaine du 06 Mars 2017"
breadcrumb: false
tags:
    - esgi
    - langage_scripting_shell_python
    - cours
categories:
    - exercice_langage_scripting_shell_python
show_meta: false
---

<!-- TOC depthFrom:1 depthTo:6 withLinks:1 updateOnSave:1 orderedList:0 -->

- [TP Pyhton](#tp-pyhton)
	- [Exerice 1 :](#exerice-1-)
	- [Exerice 2 :](#exerice-2-)
	- [Exerice 3 :](#exerice-3-)
	- [Exerice 4 :](#exerice-4-)
	- [Exercice 5 :](#exercice-5-)
	- [Exercice 6](#exercice-6)
	- [Exercice 7](#exercice-7)
	- [Exercice fin de projet](#exercice-fin-de-projet)

<!-- /TOC -->

# TP Pyhton

## Exerice 1 :

Tester, commenter et améliorer le code suivant :

    list1=["vendredi",19,"avril"]
    print(list1)
    print(list1[0])
    len(list1)
    list1.append(2012)
    print(list1)
    list1[3]+1
    del list1[0]
    print(list1)
    list1.insert(20,"Samedi")
    print(list1)
    print("jeudi" in list1)
    print("Samedi" in list1)
    list2=list1[1:3]
    print(list2)
    list3=list1[:2]
    list4=list1[1:]
    print(list3)
    print(list4)
    list3=list3+[2015]
    print(list3)
    list5=5*list1
    print(list5)
    list1.extend([3,4])
    print(list1)
    list6=list1.pop(0)
    print(list5)

Résultat :

    ['vendredi', 19, 'avril']
    vendredi
    ['vendredi', 19, 'avril', 2012]
    [19, 'avril', 2012]
    [19, 'avril', 2012, 'Samedi']
    False
    True
    ['avril', 2012]
    [19, 'avril']
    ['avril', 2012, 'Samedi']
    [19, 'avril', 2015]
    [19, 'avril', 2012, 'Samedi', 19, 'avril', 2012, 'Samedi', 19, 'avril', 2012, 'Samedi', 19, 'avril', 2012, 'Samedi', 19, 'avril', 2012, 'Samedi']
    [19, 'avril', 2012, 'Samedi', 3, 4]
    [19, 'avril', 2012, 'Samedi', 19, 'avril', 2012, 'Samedi', 19, 'avril', 2012, 'Samedi', 19, 'avril', 2012, 'Samedi', 19, 'avril', 2012, 'Samedi']

Correction :

    list1=["vendredi",19,"avril"] # Création d'une liste de 3 objets différents
    print(list1)                  # Affiche du contenu de la liste1
    print(list1[0])               # Affichage de 1er objet de la liste1
    **print (len(list1))**        # Affichage de la taille 3 de la liste1
    list1.append(2012)            # Ajout de l'objet entier 2012 à la fin (append = a la fin) de la liste1
    print(list1)                  # Affiche du contenu de la liste1
    list1[3]+1                    # Addition de l'objet entier 2012 et l'objet 1
    del list1[0]                  # Suppression de l'objet d'indice zero (vendredi)
    print(list1)                  # Affiche du contenu de la liste1
    list1.insert(20,"Samedi")     # Ajout de l'objet (samedi) à la fin de la liste(insert = à la 20ème position)
    print(list1)                  # Affiche du contenu de la liste1
    **print (list1[3])**          # Affichage et vérification de l'élément 4
    print("jeudi" in list1)       # Affichage de la vérification (jeudi est dans la liste = Faux)
    print("Samedi" in list1)      # Affichage de la vérification (samedi est dans la liste = Vrai)
    list2=list1[1:3]              # Créaion de la liste2 d'éléments 1&2 (3 exclus) à partir de la liste1
    print(list2)                  # Affichage du contenu de la liste2
    list3=list1[:2]               # Création de la liste3 d'élements 0 à 1 (2 exclus) à partir de la liste1
    list4=list1[1:]               # Création de la liste4 d'éléments 1 à la fin à partir de la liste1
    print(list3)                  # Affichage du contenu la liste3
    print(list4)                  # Affichage du contenu de la liste4
    list3=list3+[2015]            # Ajout de l'objet (2015) à la liste3
    print(list3)                  # Affichage de la liste3
    list5=5*list1                 # Création de la liste5, 5 fois la liste1
    print(list5)                  # Affichage de la liste5
    list1.extend([3,4])           # Ajout à la liste1 l'élément 3 et 4
    print(list1)                  # Affichage de la liste1
    list6=list1.pop(0)            # Création de la liste6 en suppression de l'élément d'indice zero (19)
    **print(list6)**              # Affichage de la liste6
    **print(list1)**              # Affichage de la liste1

**Résultat :**

    ['vendredi', 19, 'avril']
    vendredi
    3
    ['vendredi', 19, 'avril', 2012]
    [19, 'avril', 2012]
    [19, 'avril', 2012, 'Samedi']
    Samedi
    False
    True
    ['avril', 2012]
    [19, 'avril']
    ['avril', 2012, 'Samedi']
    [19, 'avril', 2015]
    [19, 'avril', 2012, 'Samedi', 19, 'avril', 2012, 'Samedi', 19, 'avril', 2012, 'Samedi', 19, 'avril', 2012, 'Samedi', 19, 'avril', 2012, 'Samedi']
    [19, 'avril', 2012, 'Samedi', 3, 4]
    19
    ['avril', 2012, 'Samedi', 3, 4]

## Exerice 2 :

Définir la liste : list=[17,20,38,26,68,45]
Effectuer les actions suivantes :
 - Trier et afficher la liste
 - Ajouter l’élément 17 puis afficher
 - Calculer le nombre d’apparition de l’élément 17
 - Renverser et afficher la liste
 - Afficher la taille de la liste
 - Afficher l’indice de l’élément 10
 - Enlever l’élément 38 et afficher la liste
 - Afficher le sous liste du 3ieme au 4ieme élément
 - Afficher la sous liste du début au 2ieme élément
 - Afficher la sous liste du 3ieme liste à la fin de la liste
 - Afficher le dernier élément en utilisant un indiçage négatif

     Ma_liste=[17,20,38,26,68,45]

     print("Ma liste initiale :", Ma_liste)                                   # Affiche l'objet Ma_liste
     Ma_liste.sort()                                                          # Trie l'objet Ma_liste
     print("Ma liste triée :", Ma_liste)                                      # Affiche l'objet Ma_liste trié
     print("Nombre d'occurences de 17 :", Ma_liste.count(17))                 # Affiche le nombre d'occurence de la valeur défini (17)
     Ma_liste.reverse()                                                       # Inverse l'ordre de la liste
     print("Ma liste inversée :", Ma_liste)                                   # Affiche l'objet Ma_liste inversé
     print("Taille de la liste :", len(Ma_liste))                             # Affiche la taille de l'objet Ma_liste

     #print(Ma_liste.index(10))  #10 n'existe pas? Exception générée

     if 10 in Ma_liste:                                                       # Si l'indice 10 existe dans l'objet Ma_liste
         print("True", Ma_liste.index(10))                                    # Alors affiche Vrai
     else :                                                                   # Sinon
         print("False, l'élément 10 n'existe pas dans ma liste)               # Affiche Faux et informe l'utilisateur

     print("Indice de 38 :", Ma_liste.index(38))                              # Affiche l'indice 38 dans l'objet Ma_liste
     Ma_liste.remove(38)                                                      # Supprime l'indice 38
     print("Ma liste après suppression de 38 :", Ma_liste)                    # Affiche l'objet Ma_liste sans l'indice 38
     print("Du 3ème au 4ème élément :")                                       # Affiche la phrase
     print(Ma_liste[2:4])                                                     # Affiche l'objet Ma_liste de l'élément 3 à 4  (26 20)  
     print("La sous liste à partir du début au 2ème élément d'indice 1 :")    # Affiche la phrase
     print(Ma_liste[:2])                                                      # Affiche l'objet Ma_liste du début à l'élément 2 (68 45)
     print("La sous liste à partir du 3ème élément jusqu'à la fin")           # Affiche la phrase
     print(Ma_liste[2:])                                                      # Affiche l'objet Ma_liste du 3ème élément à la fin (26 20 17)
     print("Dernier élément par indiçage négatif")                            # Affiche la phrase
     print(Ma_liste[-1])                                                      # Affiche Le dernier élément par indice négatif (17)

**Résultat :**

    Ma liste initiale : [17, 20, 38, 26, 68, 45]
    Ma liste triée : [17, 20, 26, 38, 45, 68]
    Nombre d'occurences de 17 : 1
    Ma liste inversée : [68, 45, 38, 26, 20, 17]
    Taille de la liste : 6
    False, l'élément 10 n'existe pas dans ma liste
    Indice de 38 : 2
    Ma liste après suppression de 38 : [68, 45, 26, 20, 17]
    Du 3ème au 4ème élément :
    [26, 20]
    La sous liste à partir du début au 2ème élément d'indice 1 :
    [68, 45]
    La sous liste à partir du 3ème élément jusqu'à la fin
    [26, 20, 17]
    Dernier élément par indiçage négatif
    17


## Exerice 3 :

Utiliser une liste en intension pour obtenir la liste [ad,ae,bd,be,cd,ce] à partir des chaînes abc et de en utilisant une version en extension avec deux boucles for imbriquées, puis une version en intension.

    my_list=[]                       #déclaration de la liste vide

    print("2 versions avec deux boucles imbriquées :")


    #--------------------- Version 1


    #list1=['a','b','c']
    #list2=['d','e']
    #
    #for i in list1:
    #    for j in list2:
    #        my_list.append(i+j)
    #
    #print(my_list)


    #--------------------- Version 2


    for i in "abc":
        for j in "de":
            my_list.append(i+j)
    print(my_list)


    #--------------------- Version en intension, compactée


    print("\nVersion en intention\n")

    ma_liste=[i+j for i in "abc" for j in "de"]   #variable ma_liste initialisée en même temps

    print(ma_liste)

**Résultat:**

2 versions avec deux boucles imbriquées :
['ad', 'ae', 'bd', 'be', 'cd', 'ce']

Version en intention

['ad', 'ae', 'bd', 'be', 'cd', 'ce']

## Exerice 4 :

Ecrire une fonction nbr_mots qui admet comme argument une chaîne de caractères et qui renvoie un dictionnaire contenant la fréquence d’apparition de chaque mot de la chaîne.     
Exemple « Mais ou est passé Paul ? Paul est au ciné »

    Donc Dico[paul]=2


    # Version programme principal

    Mon_dico={}
    Phrase=input("Saisir votre phrase :")
    Ma_liste=Phrase.split()
    print(Ma_liste)

    # Utiliser count()
    for mot in Ma_liste:
        Mon_dico[mot]=Ma_liste.count(mot)
    print(" Voici Mon_dico version 1:\n ")
    print(Mon_dico)

    # ou bien autre possibilité    
    ##for mot in Ma_liste:
    ##    if mot in Mon_dico:
    ##        Mon_dico[mot]+=1
    ##    else:
    ##        Mon_dico[mot]=1
    ##
    ##print(" Voici Mon_dico version 2 :\n ")
    ##print(Mon_dico)



    #####################  version  Méthode ############################

    def CptMots(texte):  # fonction compte mots
        dico={}
        listeMots=texte.split()  # extraire les mots de la chaine récupérés dans la liste
        print(listeMots)
        # Une version sans le count()
        for mot in listeMots:
            if mot in dico:
                dico[mot]=dico[mot]+1
            else:
                dico[mot]=1
        print("Voici le second dictionnaire :\n")
        print(dico, '\n')
        return dico


    # Programme principal
    resultat=CptMots("je ne veux pas aller ou vous allez , je ne veux pas ")
    print(resultat)

    #  autre version
    print("Affichage des clés/valeurs :\n")
    for clé in resultat.keys():
        print("Clé:", clé ,"--> Valeur correspondante :", resultat[clé])
    print("--------------------------------------------------\n")

    print("Affichage des clés :\n")
    for valeur in resultat.values():
        print("-->", valeur)

    dic={}
    clé="toto "+"titi"  # clé composée
    dic[clé]="pwd1"
    print(dic.keys())

**Résultat :**

    Saisir votre phrase :Mais ou est passé Paul ? Paul est au ciné

    ['Mais', 'ou', 'est', 'passé', 'Paul', '?', 'Paul', 'est', 'au', 'ciné']
     Voici Mon_dico version 1:

    {'Mais': 1, 'ou': 1, 'est': 2, 'passé': 1, 'Paul': 2, '?': 1, 'au': 1, 'ciné': 1}
    ['je', 'ne', 'veux', 'pas', 'aller', 'ou', 'vous', 'allez', ',', 'je', 'ne', 'veux', 'pas']
    Voici le second dictionnaire :

    {'je': 2, 'ne': 2, 'veux': 2, 'pas': 2, 'aller': 1, 'ou': 1, 'vous': 1, 'allez': 1, ',': 1}

    {'je': 2, 'ne': 2, 'veux': 2, 'pas': 2, 'aller': 1, 'ou': 1, 'vous': 1, 'allez': 1, ',': 1}
    Affichage des clés/valeurs :

    Clé: je --> Valeur correspondante : 2
    Clé: ne --> Valeur correspondante : 2
    Clé: veux --> Valeur correspondante : 2
    Clé: pas --> Valeur correspondante : 2
    Clé: aller --> Valeur correspondante : 1
    Clé: ou --> Valeur correspondante : 1
    Clé: vous --> Valeur correspondante : 1
    Clé: allez --> Valeur correspondante : 1
    Clé: , --> Valeur correspondante : 1
    --------------------------------------------------

    Affichage des clés :

    --> 2
    --> 2
    --> 2
    --> 2
    --> 1
    --> 1
    --> 1
    --> 1
    --> 1
    dict_keys(['toto titi'])

## Exercice 5 :

1. Proposer une implémentation d’un annuaire de gestion des utilisateurs d’un réseau local avec le minimum (login/Password) avec le password hashé MD5.
2. Justifier le choix de la structure de données.

Minimum fonctionnel attendu : Création/consultation/MAJ et la suppression d’un user.

## Exercice 6

Génération de mots de passe aléatoire:

    ###########Exemple de génération aléatoire de mots de passe###########
    import random
    import string

    liste_caractères=string.ascii_letters+string.digits
    print("Les caractères utilisés", liste_caractères)

    passwd=""
    for i in range(8):
        passwd+=liste_caractères[random.randint(0, len(liste_caractères)-1)]

    print("Le Mot de pass généré :",passwd)


    ###########Exemple de code de hashage###########
    import hashlib

    ###########hashage avec md5###########
    print(dir(hashlib))
    m=hashlib.md5()  # m object à hasher
    m.update(b'1ier message')
    m.update(b'2ieme message')

    print(" le hasage:",m.digest())
    print('taille du hasché 1 :' ,m.digest_size)
    print('taille bloc utilisé par md5 :', m.block_size)

    ###########Hashage avec un autre alogorithme en version hexadécimal : sha224###########
    d=hashlib.sha224()
    d.update(b'1ier message a hasher 2ieme message a hasher')

    print("le hashage :", d.hexdigest())
    print('taille du hasché 2 :' ,d.digest_size)
    print('taille bloc utilisé par sha224 :', d.block_size)

    ###########hexdigest() méthode similaire à digest() mais renvoie une chaine en hexa###########
    ###########plus longue , digest() renvoie des bytes###########

    ###########vérification de l'intégration d'un mot de passe après un test de saisie 3 fois###########

    import hashlib

    from getpass import getpass
    pwd = getpass("Tapez le mot de passe :  ")

    mot_de_passe = b"ESGI2017"  # mot de passe d'accès stocké

    mot_de_passe_chiffre = hashlib.md5(mot_de_passe).hexdigest()
    print("mot de pass hashé: " , mot_de_passe_chiffre)

    for i in range(3):
        #saisie à améliorer avec IDLE
        #pwd = getpass("Tapez le mot de passe :  ")
        pwd=input("Tapez le mot de passe :")
        # On encode la saisie pour avoir un type bytes ou octets
        pwd = pwd.encode()

        pwd_chiffre = hashlib.md5(pwd).hexdigest()
        if pwd_chiffre == mot_de_passe_chiffre:
            print("Mot de passe correct.")
            break
        else:
            print("Mot de passe incorrect.")

## Exercice 7

Programmation réseau:

**Serveur basique**

    ###############################################
    # Mise en place d'un serveur simple
    # simulation d'une connexion client/serveur
    #"""""""""""""""""  verson basique """""""""""#

    import socket  # importation du module socket
    import sys

    # les paramètres du serveur en local pour le test
    HOST='127.0.0.1'     # adresse IP du serveur
    PORT=8093           # port d'écoute du serveur
    TAILLE_BUFFER=1024   # taille max à recevoir, par défaut


    try :
    # création d'un socket
      Mysocket=socket.socket(socket.AF_INET, socket.SOCK_STREAM) # famille et mode

    # liaison du scoket à une adresse IP et un port
      Mysocket.bind((HOST, PORT))

    except socket.error:
      print("Problème de socket !!!")
      sys.exit()

    # boucle de traitement tant qu'il y a des clients connectés
    while 1 :   # ou while True
        print(">>> Serveur prêt, en attente d'un client...")

        Mysocket.listen(5)  # écoute d'une connexion

    # établissement de la connexion
        connexion,adresse=Mysocket.accept()
        print(">>> Connexion client réussie, adresse IP %s, port %s \n" % (adresse[0], adresse[1]))

    # dialogue avec le client, envoi de message en byte
        connexion.send(b"hello client")
        print(">>> Vous étes sur les serveur, prêt à recevoir vos msg")
        print(">>> Tapez FIN ou rien si vous souhaitez interrompre la connexion")

    # réception de message du client
        msgClient=connexion.recv(TAILLE_BUFFER)  # réception de 1024 caractères
        print('>>> C:' ,msgClient.decode())

    # boucle d'échange avec le client
        while 1 :  # ou while True

                 if msgClient==b"FIN" or msgClient==b"":
                        break

                 msgServer=input(">>> ")
                 msgServer=msgServer.encode()  # encodage en byte
                 print(">>> Envoi vers le client")
                 connexion.send(msgServer)             
                 msgClient=connexion.recv(TAILLE_BUFFER)
                 print(">>> Reception du client")
                 print(msgClient.decode())  # décodage inverse

    # fermeture de la connexion
        connexion.send(b"Au revoir")
        print(">>> connexion interompue par le client!!!!")
        connexion.close()
        ch=input("<R>ecommencer <T>erminer?")
        if ch==b'T':
            print('Fin des connexions.')
            break
    Mysocket.close()

Résultat:

    >>> Serveur prêt, en attente d'un client...
    >>> Connexion client réussie, adresse IP 127.0.0.1, port 50148

    >>> Vous étes sur les serveur, prêt à recevoir vos msg
    >>> Tapez FIN ou rien si vous souhaitez interrompre la connexion
    >>> C: hello serveur                 

**Client basique**

    ###############################################
    # Mise en place d'un client simple
    # simulation d'une connexion client/serveur
    #"""""""""""""""""  version basique """""""""""#

    import socket, sys

    # création d'un socket pour la connexion avec le serveur en local
    sock=socket.socket(socket.AF_INET, socket.SOCK_STREAM)

    try:
    # connexion au serveur, bloc surveillé, et gestion de l'exception
        sock.connect(('127.0.0.1',8093))

    except socket.error:
       print("la connexion a échoué.......")
       sys.exit()

    print(">>> Connexion établie avec le serveur...")

    # Envoi et réception de messages en byte
    sock.send(b"hello serveur")
    msgServer=sock.recv(1024) # taille par défaut

    print(">>> S :", msgServer.decode())

    while 1:

             if msgServer==b'FIN' or msgServer==b'':
                  break   

             msgClient=input(">>> ")
             msgClient=msgClient.encode()  # encodage en byte
             print(">>> Envoi vers le serveur")
             sock.send(msgClient)         
             msgServer=sock.recv(100)
             print(">>> Reception du serveur")
             print(msgServer.decode())  # décodage inverse

    print (">>> Connexion interrompue par le serveur!!!")
    sock.close()

Résultat:

    >>> Connexion établie avec le serveur...
    >>> S : hello client
    >>> coucou
    >>> Envoi vers le serveur
    >>> Reception du serveur

## Exercice fin de projet

Serveur de fichier FTP partagé quelque soit le nombre de clients. (Serveur FTP déjà existant)
Dans le réseau FTP, avoir également un serveur admin avec plusieurs fonctions:

 - Gestion des utilisateurs
 - Gestion des versions FTP
 - Scan de ports
 - Simulation Force-Brute (s'introduire en essayant de casser le mdp)
 - Eventuellement stock des logs (optionnelle)
