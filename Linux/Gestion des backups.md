# Gestion des backups

* Rsync : C'est un service open-source permettant de sauvegarder et restaurer des données. Celles-ci peuvent être stockées localement ou externalisées.

Rsync est utilisé par Deja Dup et Duplicity qui sont des outils graphiques de backup sur Unbuntu.

Pour plus de sécurité il est possible de chiffré ces backups en utilisant des solutions complémentaire comme 

* GnuPG
* eCryptfs
* LUKS

La tâche de sauvegarde peut être automatiser en créant un script qui sera ensuite exécuté de manière planifié soit via "systemd" soit via "crontab" par exemple.