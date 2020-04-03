# Protocole JOCC 0.9 

**Auteur: [prénom] [nom] (`sacha.perdrizat@heig-vd.ch`)**

## Introduction

Cette spécification de protocol permettra l'implémentation d'un serveur de blagues, dit JOCC sur un réseau TCP/IP

### Objectif général


## Description du protocol

A vous de structurer ce document, en utilisant plusieurs sections. Une de ces sections doit être consacrée à la gestion de l'état, où vous nous expliquez si votre protocole est avec ou sans état, et pourquoi.

### 1. Stateful ou Stateless?

J'ai choisi une implémentation de type stateless, ainsi __tout__ les échange seront indépendant les un des autre et les informations nécéssaire au bon fonctionnnement seront contenue dans chaque message. 

Egalement on facilite l'extension du protocol.


### 2.  Les messages disponibles

HELLO: 
Liste les commandes disponibles du serveur

JOOC BEGIN <JOKE> END    :


Envoie d'une bague au serveur

JOOC BEGIN <JOKE> END    :




## Remarques

Si vous avez des choses à partager au sujet de l'exercice, utilisez cette dernière section.
