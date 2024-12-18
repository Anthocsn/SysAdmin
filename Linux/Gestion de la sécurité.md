# Gestion de la sécurité

## Mise à jour

Tous d'abord il faut maintenir les paquets et le system à jour :

`apt update && apt dist-upgrade`

## Général 

L'accès des utilisateurs doit être déterminé sur la base du principe du moindre privilège. Par exemple, si un utilisateur a besoin d'exécuter une commande en tant que root, alors cette commande doit être spécifiée dans la configuration sudoers au lieu de lui donner des droits sudo complets.

## Pare-feu

iptables est le parefeu linux permettant de gérer les connexions entrante et sortante.

## fail2ban

Cet outil compte le nombre de tentatives de connexion infructueuses, et si un utilisateur a atteint le nombre maximum, l'hôte qui a essayé de se connecter sera traité comme configuré.

## SSH

Si SSH est ouvert sur le serveur, la configuration doit être configurée pour interdire la connexion par mot de passe et interdire à l'utilisateur root de se connecter via SSH. Il est également important d'éviter de se connecter et d'administrer le système en tant qu'utilisateur root dans la mesure du possible et de gérer adéquatement le contrôle d'accès.

## Audit 

Il est également important d'auditer périodiquement le système pour s'assurer qu'il n'existe pas de problèmes qui pourraient faciliter l'escalade des privilèges, tels qu'un noyau obsolète, des problèmes d'autorisation de l'utilisateur, des fichiers inscribles dans le monde entier et des tâches cron mal configurées, ou des services mal configurés. De nombreux administrateurs oublient la possibilité que certaines versions du noyau doivent être mises à jour manuellement.


## SELinux

SELinux est un système MAC intégré au noyau Linux. Il est conçu pour fournir un contrôle d'accès précis sur les ressources et les applications du système. SELinux fonctionne en appliquant une politique qui définit les contrôles d'accès pour chaque processus et fichier sur le système. Il offre un niveau de sécurité plus élevé en limitant les dommages qu'un processus compromis peut causer.

## TCP wrappers

TCP wrappers est un mécanisme de sécurité utilisé dans les systèmes Linux qui permet à l'administrateur du système de contrôler quels services sont autorisés à accéder au système. Il fonctionne en restreignant l'accès à certains services en fonction du nom d'hôte ou de l'adresse IP de l'utilisateur qui demande l'accès. Lorsqu'un client tente de se connecter à un service, le système consulte d'abord les règles définies dans les fichiers de configuration des TCP wrappers pour déterminer l'adresse IP du client. Si l'adresse IP correspond aux critères spécifiés dans les fichiers de configuration, le système accordera alors au client l'accès au service. Cependant, si les critères ne sont pas remplis, la connexion sera refusée, ce qui fournira une couche de sécurité supplémentaire pour le service. Les enveloppes TCP utilisent les fichiers de configuration suivants :

* /etc/hosts.allow : Listes des ips autorisé par services.
* /etc/hosts.deny : Liste des ips bloqué par services.

![alt text](<Images/allow.png>)
![alt text](<Images/deny.png>)