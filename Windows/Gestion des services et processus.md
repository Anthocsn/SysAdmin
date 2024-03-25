# Gestion des services et processus

Gérer par :

* GUI : Services.msc
* CLI : Get-Service en powershell

Certains services ne peuvent pas être redémarré. Si il y a une mise à jour ou une modification il faudra nécéssairement redémarrer l'appareil.

## Sysinternals Tools

La suite SysInternals Tools est un ensemble d'applications Windows portables qui peuvent être utilisées pour administrer les systèmes Windows (pour la plupart sans installation). 

Les outils peuvent être téléchargés à partir :

* web : https://learn.microsoft.com/fr-fr/sysinternals/downloads/sysinternals-suite
* Partage de fichier : \\live.sysinternals.com\tools


La suite comprend des outils tels que Process Explorer, une version améliorée de Task Manager, et Process Monitor, qui peuvent être utilisés pour surveiller le système de fichiers, le registre et l'activité du réseau lié à tout processus en cours d'exécution sur le système. 

Certains outils supplémentaires sont TCPView, qui est utilisé pour surveiller l'activité Internet, et PSExec, qui peut être utilisé pour gérer/se connecter aux systèmes via le protocole SMB à distance.


## task Manager 

Windows Task Manager est un outil puissant pour gérer les systèmes Windows. Il fournit des informations sur les processus d'exécution, les performances du système, les services d'exécution, les programmes de démarrage, les utilisateurs connectés/les processus utilisateur connectés et les services.

Gérer par :

* GUI : Depuis CTRL + ALT + SUPPR
* CLI : taskmgr

## Local Security Authority Subsystem Service (LSASS) 

Vérifie leur tentative de connexion et crée des jetons d'accès en fonction des niveaux d'autorisation de l'utilisateur. LSASS est également responsable des modifications du mot de passe du compte utilisateur. Tous les événements associés à ce processus (tentatives de connexion/déconnexion, etc.) sont enregistrés dans le journal de sécurité de Windows. 

LSASS est une cible de valeur extrêmement élevée car plusieurs outils existent pour extraire à la fois du texte clair et des informations d'identification hachées stockées en mémoire par ce processus.

## Service Permissions

