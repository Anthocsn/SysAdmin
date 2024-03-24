# Gestion des tâches

## Systemd et Crontab

Ce sont 2 outils qui peuvent être utilisé pour créer des tâches planifiées. La principale différences entre les 2 outils se trouve au niveau de la configuration.

* systemd : Il faut créer un timer et un service script pour indiquer au service quand exécuter la tâche.
* crontab : Il faut créer un fichier fichier crontab pour indique au deamon associé quand exécuter la tâche.

### Systemd

Pour créer un timer il faut :

* Créer un dossier pour notre timer : `sudo mkdir /etc/systemd/system/mytimer.timer.d`
* Créer un fichier pour notre timer : `sudo vim /etc/systemd/system/mytimer.timer.d/mytimer.timer`


Dans le fichier timer il y 3 informations à renseigner :

* Unit : C'est une description du timer.
* Timer : C'est quand la tâche sera déclenché : X minute après le démarrage du système, à X temps d'interval etc...
* Install : Permet de définir ou installer le timer.

![alt text](</Images/timer.png>)

Pour créer un service il faut : 

* Créer un fichier de service : `sudo vim /etc/systemd/system/mytimer.timer.d/mytimer.service`

Dans le fichier timer il y 3 informations à renseigner :

* Unit : C'est une description du service.
* Service : C'est l'emplacement du script à exécuter.
* Install : Permet de définir le type de démarrage du service.

![alt text](<Images/services.png>)

Pour finir, il faut :

Redémarrer le deamon systemctl : `sudo systemctl daemon-reload`
Démarrer le service manuellement : `sudo systemctel start mytimer.service`
Activer le démarrage du service automatique : `sudo systemctel enable mytimer.service`


### Crontab 

Pour le crontab c'est un peu plus simple il suffit d'aller éditer le fichier crontab et de définir l'heure et l'interval de déclenchement en respectant la structure suivante :

![alt text](<Images/crontabstructure.png>)

![alt text](<Images/crontabfichier.png>)

* / : L'ajout d'un "/" peut être traduit par "Toutes les" ce qui veut dire dans notre exemple que le system update se fait toutes les 6 heures.
* 0 et 7 : Dans la colonne de la journée le 0 et le 7 correspondent à dimanche.

Il est aussi possible de recevoir des notifications en cas de succès ou d'erreur de la tâche.

