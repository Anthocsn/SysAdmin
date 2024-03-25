# Gestion du pare-feu

## iptables

Les composant principaux de iptables sont :

* Tables : Utilisées pour organiser et catégoriser les règles de pare-feu
* Chains : Utilisées pour regrouper un ensemble de règles de pare-feu appliquées à un type spécifique de trafic réseau.
* Rules : Les règles définissent les critères de filtrage du trafic réseau et les actions à prendre pour les paquets qui correspondent aux critères.
* Matches : Les matches sont utilisées pour correspondre à des critères spécifiques de filtrage du trafic réseau, tels que les adresses IP source ou de destination, les ports, les protocoles, et plus encore.
* Targets : Les targets spécifient l'action pour les paquets qui correspondent à une règle spécifique. Par exemple, les cibles peuvent être utilisées pour accepter, déposer ou rejeter des paquets ou les modifier d'une autre manière.

### Tables

Il existe 3 types de tables :

* filter : Pour filtrer le traffic en fonction de l'IP, du port et du protocole
* nat : Pour modifier l'ip source ou destination d'un paquet
* mangle : pour modifier les headers d'un paquet

Les tables vont donc permettre d'identifier un certains type de traffic.

### Chains

Les chains sont en quelques sorte des types de traffic réseau, on va y retrouver :

* Input : Pour le traffic entrant
* Output : Pour le traffic sortant
* Pre et Postrouting : Pour le traffic arrivant avant ou après la règle de routage

Chaque tables a des chains qui vont avec. 

### Rules et targets

Les règles Iptables sont utilisées pour définir les critères de filtrage du trafic réseau et les actions à prendre pour les paquets qui correspondent aux critères. 

Les règles sont ajoutées aux chaînes à l'aide de l'option -A suivie du nom de la chaîne, et elles peuvent être modifiées ou supprimées à l'aide de diverses autres options.

Les targets correspondent à l'action à entreprendre :

* ACCEPT : Pour accepter le traffic
* DROP : Pour bloquer le traffic 

### Matchs

Ce sont l'ensemble des critères qui permettent d'appliquer de configurer une rules avec une target associé.

### Résumé

Pour autoriser ou refuser du traffic on va créer une "rules".

Cette "rules" va s'appliquer si il y a "match" avec un des critère choisit.

Une fois que la règle s'applique, c'est la targer qui défini l'action à faire sur le traffic (Autorisé, bloqué...)

Pour ne pas que la règle s'applique n'importe quand, on va l'attribuer à une "chains" qui peut être sous le traffic entrant, sortant ou autres.

Exemple `iptables -A INPUT -p tcp --dport 22 -j ACCEPT`

* iptable -A : Permet de créer une rules
* INPUT : Permet de choisir la chaine (Ici le traffic entrant)
* -p tcp --dport 22 : Permet de choisir le critère à matcher
* -j ACCEPT : Permet de choisir l'action (La target)
