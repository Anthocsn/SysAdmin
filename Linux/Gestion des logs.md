# Gestion des logs

Afin d'assurer la sécurité d'un système Linux, il est important de configurer correctement les journaux du système. Cela comprend la définition des niveaux de journal appropriés, la configuration de la rotation des journaux pour éviter que les fichiers journaux ne deviennent trop volumineux et la garantie que les journaux sont stockés en toute sécurité et protégés contre tout accès non autorisé. 

En outre, il est important d'examiner et d'analyser régulièrement les journaux pour identifier les risques potentiels pour la sécurité et répondre à tout événement de sécurité en temps opportun. Il existe plusieurs types de journaux système sous Linux, y compris :

* Kernel Logs
* System Logs
* Authentication Logs
* Application Logs
* Security Logs


## Kernel Logs

Ces journaux contiennent des informations sur le noyau du système, y compris les hardware drivers, system calls, and kernel events. Ils sont stockés dans : `/var/log/kern.log`.

Par exemple, les journaux du noyau peuvent révéler la présence de pilotes vulnérables ou obsolètes qui pourraient être ciblés par les attaquants pour accéder au système. Ils peuvent également fournir des informations sur les plantages du système, les limitations des ressources et d'autres événements qui pourraient conduire à un déni de service ou à d'autres problèmes de sécurité. En outre, les journaux du noyau peuvent nous aider à identifier les appels système suspects ou d'autres activités qui pourraient indiquer la présence de logiciels malveillants ou d'autres logiciels malveillants sur le système.

## System Logs

Ces journaux contiennent des informations sur les événements au niveau du système, tels que les démarrages et les arrêts du service, les tentatives de connexion et les redémarrages du système. Ils sont stockés dans le fichier `/var/log/syslog`.

En analysant les tentatives de connexion, les démarrages et les arrêts du service, et d'autres événements au niveau du système, nous pouvons détecter tout accès ou activité possible sur le système.

## Authentication Logs

Ces journaux contiennent des informations sur les tentatives d'authentification de l'utilisateur, y compris les tentatives réussies et échouées. Ils sont stockés dans le fichier `/var/log/auth.log`.

 Il est important de noter que bien que le fichier /var/log/syslog puisse contenir des informations de connexion similaires, le fichier /var/log/auth.log se concentre spécifiquement sur les tentatives d'authentification de l'utilisateur, ce qui en fait une ressource plus précieuse pour identifier les menaces de sécurité potentielles.

## Application Logs

Ces journaux contiennent des informations sur les activités d'applications spécifiques s'exécutant sur le système. Ils sont souvent stockés dans leurs propres fichiers, tels que `/var/log/apache2/error.log` pour le serveur web Apache ou `/var/log/mysql/error.log` pour le serveur de base de données MySQL.

En examinant ces journaux, nous pouvons identifier des vulnérabilités ou des erreurs de configuration potentielles. Par exemple, les journaux d'accès peuvent être utilisés pour suivre les demandes faites à un serveur Web, tandis que les journaux d'audit peuvent être utilisés pour suivre les modifications apportées au système ou à des fichiers spécifiques. Ces journaux peuvent être utilisés pour identifier les tentatives d'accès non autorisées, l'exfiltration de données ou toute autre activité suspecte.


Sur les systèmes Linux, la plupart des services courants ont des emplacements par défaut pour les journaux d'accès, par exemple `/var/log/apache2/access.log`

## Security Logs

Ces journaux de sécurité et leurs événements sont souvent enregistrés dans une variété de fichiers journaux, en fonction de l'application ou de l'outil de sécurité spécifique utilisé. 

Par exemple, l'application Fail2ban enregistre les tentatives de connexion échouées dans le fichier `/var/log/fail2ban.log`.


Il est important de se familiariser avec les emplacements par défaut pour les journaux d'accès et autres fichiers journaux sur les systèmes Linux, car ces informations peuvent être utiles lors de l'exécution d'une évaluation de sécurité ou d'un test de pénétration. En comprenant comment les événements liés à la sécurité sont enregistrés et stockés, nous pouvons analyser plus efficacement les données du journal et identifier les problèmes de sécurité potentiels.
