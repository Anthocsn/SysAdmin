# RWX

* R : Permet de lire le contenue d'un fichier.
* W : Permet de créer, supprimer et renommer un dossier ou un fichier.
* X : Permet de traverser et d'accéder au contenu d'un dossier. Cela ne permet pas d'éxécuter un fichier qui se trouve à l'intérieur. Pour ça il faut avoir des droits d'éxécution sur le fichier en question.

# Applications des permissions

Les permissions s'applique au propriétaire, groupes et autres.

![alt text](<Images/Permissions.png>)

# Changer les permissions

Les permissions se changent avec la commande `chmod` en ajoutant avec `+` ou en supprimant avec `-` les droits R, W ou X au proriétaire `O`, au groupe `g` ou aux autres `a`

Par exemple pour ajouter les droits de lectures aux "autres" il faut utiliser la commande :

`chmod a+r file.txt`

Il est également possible de le faire en utilisant une notation binaire. Le premier chiffre correspond au propriétaire, le 2ème au groupe et le dernier aux autres.

`chmod 754 file.txt`

![alt text](<Images/Notation Binaire.png>)

# Changement de propriétaire

Pour changer l'utilisateur ou le groupe propriétaire il faut utiliser la commande `chown`

Exemple : `chown newuser:newgroupe file.txt`

# SUID et SGID

