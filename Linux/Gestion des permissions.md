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

# SUID (Set User Id) et SGID (Set Group Id)

Lorsque le SUID ou le SGID est paramètré sur un fichier cela permet à n'importe quel utilisateur ayant accés au fichier de l'éxécuter avec les droits du propriétaire du fichier. La lettre `s` est utilisé à la place du `x` dans les droits d'accès.

Cela peut créer une grosse faille de sécurité car certaines applications permettent l'exécution d'un shell et si le propriétaire est root cela permet à n'importe qui d'ouvrir un shell en tant que root.

# Sticky Bit

Le sticky Bit peut être activé sur un dossier pour ajouter une couche de sécurité supplémentaire en n'autorisant uniquement le propriétaire, le propriétaire du dossier ou l'utilisateur root à renommer ou supprimer les fichiers dans un dossier.

Le sticky Bit est activé lorsqu'il y a un `t` à la fin des permissions.

Par exemple `rwxrwxrwxt` ou `rwxrwxrwxT`

* Si le `t` est en minuscule c'est que le Sticky Bit a été activé.
* Si le `T`est en majuscule c'est que tous les autres utilisateurs n'ont pas les droits d'execution et ne peuvent donc pas voir le contenu du dossier.