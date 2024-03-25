# Gestion des permissions

## Types de permissions

* Full Control : Permet de lire, d'écrire, de modifier, de supprimer des fichiers/dossiers.
* Modify : Permet de lire, d'écrire et de supprimer des fichiers/dossiers.
* List Folder Contents : Permet de visualiser et de répertorier les dossiers et les sous-dossiers ainsi que l'exécution de fichiers. Les dossiers n'héritent que de cette autorisation.
* Read and Execute : Permet d'afficher et d'énumérer les fichiers et les sous-dossiers ainsi que l'exécution de fichiers. Les fichiers et dossiers héritent de cette autorisation.
* Write : Permet d'ajouter des fichiers à des dossiers et des sous-dossiers et d'écrire dans un fichier.
* Read : Permet de visualiser et de répertorier les dossiers et les sous-dossiers et de visualiser le contenu d'un fichier.
* Traverse Folder : Cela permet ou nie la possibilité de se déplacer dans les dossiers pour atteindre d'autres fichiers ou dossiers.


Les fichiers et dossiers héritent des autorisations NTFS de leur dossier parent pour faciliter l'administration, de sorte que les administrateurs n'ont pas besoin de définir explicitement des autorisations pour chaque fichier et dossier, car cela prendrait beaucoup de temps. 

Si les autorisations doivent être définies explicitement, un administrateur peut désactiver l'héritage des autorisations pour les fichiers et dossiers nécessaires, puis définir les autorisations directement sur chacun d'eux.

## Integrity Control Access Control List (icacls)

Les autorisations NTFS sur les fichiers et dossiers dans Windows peuvent être gérées à l'aide de l'interface graphique de l'Explorateur de fichiers sous l'onglet Sécurité. 

Outre l'interface graphique, nous pouvons également atteindre un niveau de granularité élevé sur les autorisations de fichiers NTFS dans Windows à partir de la ligne de commande à l'aide de l'utilitaire `icacls`. 

Le niveau d'accès aux ressources est répertorié après chaque utilisateur. Les paramètres d'héritage possibles sont :

* (CI): container inherit
* (OI): object inherit
* (IO): inherit only
* (NP): do not propagate inherit
* (I): permission inherited from parent container

![alt text](<Images/permissions.png>)

Les autorisations d'accès de base sont les suivantes : 

* F : full access
* M :  modify access
* RX :  read and execute access
* W :  write-only access
* R :  read-only access
* D :  delete access
* N :  no access


En utilisant la commande `icacls c:\users /grant joe:f`, nous pouvons accorder à l'utilisateur joe un contrôle total sur le répertoire.

Mais étant donné que (oi) et (ci) n'ont pas été inclus dans la commande iln'aura que des droits sur le dossier c:\users, mais pas sur les sous-répertoires de l'utilisateur et les fichiers qu'ils contiennent.

Pour supprimer les droits on utile la commande `icacls c:\users /remove joe`.



