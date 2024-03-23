# RWX

* R : Permet de lire le contenue d'un fichier.
* W : Permet de créer, supprimer et renommer un dossier ou un fichier.
* X : Permet de traverser et d'accéder au contenu d'un dossier. Cela ne permet pas d'éxécuter un fichier qui se trouve à l'intérieur. Pour ça il faut avoir des droits d'éxécution sur le fichier en question.

# Applications des permissions

Les permissions s'applique au propriétaire, groupes et autres.

![alt text](<Images\Permissions.png>)

# Changer les permissions

Les permissions se changent avec la commande `chmod` en ajoutant avec `+` ou en supprimant avec `-` les droits R, W ou X au proriétaire `O`, au groupe `g` ou aux autres `a`

Par exemple pour ajouter les droits de lectures aux "autres" il faut utiliser la commande `chmod a+r file.txt`