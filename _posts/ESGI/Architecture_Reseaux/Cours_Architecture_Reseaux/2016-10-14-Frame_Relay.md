---
layout: page
title:  "Cours Frame Relay"
teaser: "Cours sur Frame Relay lors de la semaine du 10 Octobre 2016"
breadcrumb: false
tags:
    - esgi
    - architecture_reseaux
    - cours
categories:
    - cours_architecture_reseaux
show_meta: false
---

# Concept

Frame realy est classé comme réseau très haut débit dans les années 90 (40 Mb).  

Frame Ralay effectue une commutation sur la base d'un numéro DLSI.  
Cesréseaux font des allocations dynamiques de la bande passante contrairement à avant ou il s'agissait de la bande passante statique.  

![Exemple1](http://portfolio.fpompey.com/images/ESGI/Exemple1-Frame_Relay.png)

# Structure générale

**UNI:**	User Interface Network  
**NNI:**	Network  Node  Interface  
**DTE:** 	Data Terminal Equipement  
**DCE:**	Data Circuit Equipement

![Exemple2](http://portfolio.fpompey.com/images/ESGI/Exemple2-Frame_Relay.png)

# Structure de la trame Frame Relay

![Exemple3](http://portfolio.fpompey.com/images/ESGI/Exemple3-Frame_Relay.png)

# Définitions:

**CIR:**	Committed Information Rate  
Débit moyen négocié pendant un intervalle de temps prédéfini ( intervalle Tc=Bc/CIR)

**BC:**	Committed Burst  
Nombre maximum de bits acceptés par le commutateur pendant la durée de l’intervalle de temps (Tc) de mesure du CIR

**BE:**	Excess Burst  
Nombre maximum de bits acceptés au dessus di CIR par le commutateur pendant la durée de l’intervalle de temps Tc de mesure du CIR  

**DE:**	Discard Eligibility  
Le commutateur éliminera en priorité les trames marquées (DE=1) s’il y a congestion

**FECN:** Forward Explicit Congestion Notification
Quand le commutateur reconnait un état de congestion dans le résezau, il transmet une trame avec FFECN positionné vers la destination

**BECN:** Backward Explicit Notification Congestion  
Quant le commutateur reconnait un état de congestion dans le réseau, il transmet une trame avec BECN positionné vers la source
