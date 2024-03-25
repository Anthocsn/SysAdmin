# Gestion du réseau

## Interface Réseau

### IP
Pour afficher des informations ou configurer une interface réseau il faut utiliser la commande `ifconfig` ou sa nouvelle version `ip`. Même si `ifconfig` est encore très utilisé nous allons utiliser `ip` pour l'exemple.

* ip addr : Permet d'afficher les informations d'une interface réseau.
* ip link set eth0 up : Permet d'activer une interface réseau.
* ip addr add 192.../24 dev eth0 : Permet de modifier l'IP et le masque d'une interface réseau.
* ip route add default via 192.168.1.1 eth0 : Permet de définir la gateway


### DNS

Pour ajouter un serveur DNS il faut éditer le fichier dans /etc/resolv.conf.

### Vérification

Pour vérifier que les changements sont bien prises en compte il est possible d'aller éditer le fichier suivants : /etc/network/interfaces

Celui-ci regroupe toutes les configurations pour chaque interfaces.

![alt text](<Images/interfaces.png>)


Pour redémarrer les service réseau : `systemctl restart networking`


## Network Access Control (NAC)

NAC est un système de sécurité qui garantit que seuls les appareils autorisés et conformes ont accès au réseau, empêchant ainsi les accès non autorisés, les violations de données et d'autres menaces pour la sécurité.

Voici les différentes technologies CNA qui peuvent être utilisées pour améliorer les mesures de sécurité :

* Discretionary access control (DAC) : Ce sont les accès type RWX.
* Mandatory access control (MAC) : L'accès à une ressource n'est accordé que si le niveau de sécurité de l'utilisateur ou du processus est égal ou supérieur au niveau de sécurité de la ressource.
* Role-based access control (RBAC) : RBAC attribue des autorisations aux utilisateurs en fonction de leurs rôles au sein d'une organisation. Les utilisateurs se voient attribuer des rôles en fonction de leurs responsabilités professionnelles ou d'autres critères, et chaque rôle se voit accorder un ensemble d'autorisations qui déterminent les actions qu'ils peuvent effectuer.

## Troubleshooting 

* Ping : Permet d'envoyer des paquets de test pour voir si une machine réponds
* Traceroute : Permet de suivre le chemin emprunté par un paquet pour voir à quel niveau ça pose problème.
* netstat : Avec l'option -a permet de voir le nombre de connexion active.