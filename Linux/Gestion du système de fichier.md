# Gestion du système de fichier

## Gestion des disques

Les gestions des disques inclus :

* Les disques dur mécanique
* Les SSD
* Les disques externe 

L'outil principale pour gérer les disques s'appel "fdisk" et permet de créer, supprimer et gérer des partitions sur un disque. D'autres solutions existe comme "gpart" et "GParted".

Pour lister les disques : `sudo fdisk -l`

## Mounting

Chaque partition logique ou disque doit être assigné à un répertoire sur Linux. Le fait d'attribuer un répertoire à un disque physique ou logique s'appel "Monter le disque". Une fois le disque monté il est accessible comme n'importe quel autre dossier.

Le fichier "/etc/fstab" affiche les disques montés par défaut au démarrage du système.

`mount` est la commande permettant de monter un disque et lorsqu'on l'utilse sans argument elle permet de voir les système de fichier actuellement montés.

Pour monter un disque on utilise la commande suivante : `sudo mount <source> <destination>` :

* Source : Le disque que l'on veut monter.
* Destination : Le dossier auquel on veut le rattacher.

