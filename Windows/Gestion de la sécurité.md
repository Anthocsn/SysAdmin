# Gestion de la sécurité

## Security Identifier (SID)

Chacun des principaux de sécurité du système a un identifiant de sécurité unique (SID). Le système génère automatiquement des SID. Cela signifie que même si, par exemple, nous avons deux utilisateurs identiques sur le système, Windows peut distinguer les deux et leurs droits en fonction de leurs SID. Les SID sont des valeurs de chaîne de différentes longueurs, qui sont stockées dans la base de données de sécurité. Ces SID sont ajoutés au jeton d'accès de l'utilisateur pour identifier toutes les actions que l'utilisateur est autorisé à entreprendre.

Un SID se compose de l'autorité d'identification et de l'ID relatif (RID). Dans un environnement de domaine Active Directory (AD), le SID inclut également le SID de domaine.

## Security Accounts Manager (SAM) and Access Control Entries (ACE)

