# Gestion des services et processus

On distingue en général 2 types de services :

* Interne : Ceux requis pour le démarrage du système
* Utilisateurs : Ceux installé par l'utilisateur du système.

Certains services s'éxécute en arrière plan, sans interaction utilisateurs, c'est ce qu'on appel des "deamons" et sont identiés par la lettre "d" à la fin comme par exemple :

* SSHD : C'est le service SSH.
* systemd : C'est un Init process qui a le PID 1 et qui s'occupe de démarer et éteindre les autres services.

Tous les process ont un PID d'assigné que l'on peut voir dans "/proc"/.

SysV script est un script permettant de choisir les services à lancer au démarrage du système.


## Systemctl

systemctl permet de gérer les services avec par exemple :

* start : Pour démarrer un service.
* stop : Pour arréter un service.
* status : Pour afficher l'état d'un service.
* enable : Pour ajouter un service au SysV script et le lancer au démarrage du système.
* list-units --type=service = Pour lister tous les services


## Processus

Les processus peuvent être dans les états suivants :

* Running : Le service est en cours d'utilisation.
* Waiting : Le service est en attente d'un événement ou d'une ressource système.
* Stopped : Le service est arrété.
* Zombie : Le serice est arrété mais visible dans la liste des processus.


Les processus peuvent être contrôlé via les commandes :

* kill
* pkill
* pgrep
* killall

Pour intérragir avec un procéssus et il faut lui envoyer un signal, les plus communs sont : 


* 1	(SIGHUP) : C'est le signal envoyé lorsqu'on ferme un terminal qui gére un processus.
* 2	(SIGINT) : C'est le signal envoyé lorsqu'on fait un "CTRL + C" dans un terminal.
* 3	(SIGQUIT)  : C'est le signal envoyé quand on fait un "CTRL + D" pour quitter.
* 9	(SIGKILL) : C'est le signal envoyé pour forcer un programme à se fermer immédiatement.
* 19 (SIGSTOP) : C'est le signal envoyé pour arréter un programme normalement.
* 20 (SIGTSTP) : C'est le signal envoyé lorsqu'on fait un "CTRL + Z" dans un terminal pour suspendre un processus en cours.

Si on veut forcer un programme à se fermer immédiatement on peut donc faire un `kill 9 <PID>`

### Mettre un processus en arrière plan (Background)

En faisant un "CTRL+Z" on peut mettre en arrière plan un processus. Il est possible possible de voir la liste des processus en arrière plan via la commande `jobs`.

Cependant, en utilisant le "CTRL+Z" le processus s'arréte complétement. Pour que celui-ci continue de tourner en arrière plan il faut utiliser la commande `bg`.


### Mettre un processus au premier plan (Foreground)

Pour remettre un processus au premier plan il suffit d'utiliser la commande `fg <ID>` avec l'ID du processus à faire remonter au premier plan.

Une fois un processus mis en arrière plan il n'y a plus besoin d'intéragir avec lui et une notification sera faite par le terminal pour dire que le processus est terminé.