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