# Protocole JOCC 0.9 

**Auteur: [prénom] [nom] (`sacha.perdrizat@heig-vd.ch`)**

## Introduction

Cette spécification de protocol permettra l'implémentation d'un serveur de blagues, dit JOCC sur un réseau TCP/IP

### Objectif général


## Description du protocol

A vous de structurer ce document, en utilisant plusieurs sections. Une de ces sections doit être consacrée à la gestion de l'état, où vous nous expliquez si votre protocole est avec ou sans état, et pourquoi.

### 1. Stateful ou Stateless?

J'ai choisi une implémentation de type stateless, ainsi __tout__ les échange seront indépendant les un des autre et les informations nécessaires au bon fonctionnement seront contenue dans chaque message. 

Également cela facilitera l'extension du protocole. Chaque message ajoutant un comportement bien définit.


### 2.  Les messages disponibles

La syntaxe global des message du protocol JOCC stateless est définit ici

### IMPORTANT: la terminaison de message 

Tout les messages seront terminé avec le mot __STOP__ .

#### 2.1  HELLO

Liste les commandes disponibles du serveur

#### 2.2  SENDJOCC  "joke" USER  [TYPE]  
Ce message transmet au serveur une blague l'utilisateur dois renseigner son nom mais peux aussi donner un type de blague faculatif

Le serveur répondra par ``[OK]`` si la reception se passe bien

#### 2.3  GETJOCC [TOP] [LATEST]
Permet au client de recuperer les blagues du serveur, en spécifiant TOP il récupère les mieux noté et avec LATEST les blagues les plus récentes. 

__format de la réponse :__
```
idBlague | note | Blague | type | author
```
#### 2.4  EVAL idBlague [UP | DOWN]
Permet l'évaluation des blagues UP pour augmenter la note et DOWN pour la faire baisser

#### 2.5 GETMEMBERS [MOST | BEST]

Rend les membre ayant le plus soumis de blague (MOST) ou les membre ayant soumis les meilleurs blagues (BEST)

#### 2.8 CLOSE
Demande au serveur de fermer la connexion

#### 2.6 Message d'erreur

Si le serveur ne reçoit pas de message valide la réponse suivante sera envoyé

```
ERROR INVALID COMD
```

## EXEMPLE

```
C: HELLO STOP
S:
EVAL
GETMEMBERS
GETJOCC
SENDJOCC
STOP
C: SENDJOCC utiliser UDP pour éviter les handshake USER sacha TYPE Blague geek STOP
S:[OK]
C: CLOSE STOP
S: ferme la connexion

```

## Précision/détail technique

Ici sont ajouté toute les précisions d'ordre technique que je trouvait pertinente

- Les message ne doivent pas contenir autre chose que du code ASCII sinon ils peuvent être mal intéprétées.

