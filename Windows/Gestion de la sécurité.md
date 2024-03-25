# Gestion de la sécurité

## Security Identifier (SID)

Chacun des principaux de sécurité du système a un identifiant de sécurité unique (SID). Le système génère automatiquement des SID. Cela signifie que même si, par exemple, nous avons deux utilisateurs identiques sur le système, Windows peut distinguer les deux et leurs droits en fonction de leurs SID. Les SID sont des valeurs de chaîne de différentes longueurs, qui sont stockées dans la base de données de sécurité. Ces SID sont ajoutés au jeton d'accès de l'utilisateur pour identifier toutes les actions que l'utilisateur est autorisé à entreprendre.

Un SID se compose de l'autorité d'identification et de l'ID relatif (RID). Dans un environnement de domaine Active Directory (AD), le SID inclut également le SID de domaine.

## Security Accounts Manager (SAM) and Access Control Entries (ACE)

SAM accorde des droits à un réseau pour exécuter des processus spécifiques.

Les droits d'accès eux-mêmes sont gérés par les entrées de contrôle d'accès (ACE) dans les listes de contrôle d'accès (ACL). Les listes de contrôle d'accès contiennent des ACE qui définissent les utilisateurs, les groupes ou les processus qui ont accès à un fichier ou à l'exécution d'un processus, par exemple.

Les autorisations d'accès à un objet sécurisé sont données par le descripteur de sécurité, classé en deux types d'ACL : la liste de contrôle d'accès discrétionnaire (DACL) ou la liste de contrôle d'accès au système (SACL). Chaque thread et processus démarré ou initié par un utilisateur passe par un processus d'autorisation. Les jetons d'accès, validés par la Local Security Authority (LSA), font partie intégrante de ce processus. En plus du SID, ces jetons d'accès contiennent d'autres informations relatives à la sécurité. La compréhension de ces fonctionnalités est une partie essentielle de l'apprentissage de l'utilisation et du travail autour de ces mécanismes de sécurité pendant la phase d'escalade des privilèges.

## User Account Control (UAC)

