# Protocole JOCC 0.9 

**Auteur: [prénom] [nom] (`sacha.perdrizat@heig-vd.ch`)**

## Introduction

Cette spécification de protocol permettra l'implémentation d'un serveur de blagues, dit JOCC sur un réseau TCP/IP

### Objectif général


## Description du protocol

A vous de structurer ce document, en utilisant plusieurs sections. Une de ces sections doit être consacrée à la gestion de l'état, où vous nous expliquez si votre protocole est avec ou sans état, et pourquoi.

### 1. Stateful ou Stateless?

J'ai choisi une implémentation de type stateless, ainsi __tout__ les échange seront indépendant les un des autre et les informations nécéssaires au bon fonctionnnement seront contenue dans chaque message. 

ce sera certe gourmand en bandwith mais on facilite l'extension du protocol.


### 2.  Les messages disponibles

La syntaxe global du protocol stateless

2.1 #### HELLO: 

Liste les commandes disponibles du serveur

2.2 #### SEND  <JOKE> USER  [TYPE]   :
Ce message transmet au serveur une blague l'utilisateur dois renseigner son nom mais peux aussi donner un type de blague faculatif

2.3 #### GETJOOC [TOP] [LATEST]
Permet au client de recuperer les blagues du serveur, en spécifiant TOP il récupère les mieux noté et avec LATEST les blagues les plus récentes. 

__format de la réponse :__
```
idBlague | note | Blague | type | author
```

2.4 #### EVAL idBlague [UP | DOWN]
Permet l'évaluation des blagues UP pour augementer la note et DOWN pour la faire baisser

2.5 GETMEMBER [MOST | BEST]

Rend les mebre ayant le plus soumis de blague (MOST) ou les membre ayant soumis les meilleurs blagues (BEST)

## Remarques

Si vous avez des choses à partager au sujet de l'exercice, utilisez cette dernière section.
