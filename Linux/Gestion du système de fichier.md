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

Le fichier "/etc/fstab" affiche les disques montés par défaut au démarrage du système. Il est également possible dans ce fichier de définir les disques qui ne doivent pas être remonté automatiquement via l'option "noauto".

`mount` est la commande permettant de monter un disque et lorsqu'on l'utilse sans argument elle permet de voir les système de fichier actuellement montés.

Pour monter un disque on utilise la commande suivante : `sudo mount <source> <destination>` :

* Source : Le disque que l'on veut monter.
* Destination : Le dossier auquel on veut le rattacher.

`unmount` est la commande permettant de démonter un disque, par exemple : `sudo unmount <destination>` :

* Destination : Le dossier sur lequel a été monté le disque via la commande `mount`

## SWAP

Le swap permet d'utiliser la mémoire physique de l'ordinateur (Disque dur, SSD etc...) à la place de la mémoire RAM quand celle-ci est complétement utilisé. Cette espace doit être dédié et séparé de système de fichier principal. Pour des raisons de sécurité cette espace doit également être chiffré car des données sensible peuvent y être stocké.

Le swap est également utlisé en mode "hibernation" pour stocker les données actuellement utilisé avant de d'éteindre l'ordinateur ce qui permet de les récupérer au redémarrage du système.

* mkswap : Permet de configurer une zone de swap sur un appareil ou sur un fichier.
* swapon : Permet d'activer ou non la zone de swap.
