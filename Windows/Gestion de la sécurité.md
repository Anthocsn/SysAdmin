# Gestion de la sécurité

## Security Identifier (SID)

Chacun des principaux de sécurité du système a un identifiant de sécurité unique (SID). Le système génère automatiquement des SID. Cela signifie que même si, par exemple, nous avons deux utilisateurs identiques sur le système, Windows peut distinguer les deux et leurs droits en fonction de leurs SID. Les SID sont des valeurs de chaîne de différentes longueurs, qui sont stockées dans la base de données de sécurité. Ces SID sont ajoutés au jeton d'accès de l'utilisateur pour identifier toutes les actions que l'utilisateur est autorisé à entreprendre.

Un SID se compose de l'autorité d'identification et de l'ID relatif (RID). Dans un environnement de domaine Active Directory (AD), le SID inclut également le SID de domaine.

## Security Accounts Manager (SAM) and Access Control Entries (ACE)

SAM accorde des droits à un réseau pour exécuter des processus spécifiques.

Les droits d'accès eux-mêmes sont gérés par les entrées de contrôle d'accès (ACE) dans les listes de contrôle d'accès (ACL). Les listes de contrôle d'accès contiennent des ACE qui définissent les utilisateurs, les groupes ou les processus qui ont accès à un fichier ou à l'exécution d'un processus, par exemple.

Les autorisations d'accès à un objet sécurisé sont données par le descripteur de sécurité, classé en deux types d'ACL : la liste de contrôle d'accès discrétionnaire (DACL) ou la liste de contrôle d'accès au système (SACL). Chaque thread et processus démarré ou initié par un utilisateur passe par un processus d'autorisation. Les jetons d'accès, validés par la Local Security Authority (LSA), font partie intégrante de ce processus. 

En plus du SID, ces jetons d'accès contiennent d'autres informations relatives à la sécurité. La compréhension de ces fonctionnalités est une partie essentielle de l'apprentissage de l'utilisation et du travail autour de ces mécanismes de sécurité pendant la phase d'escalade des privilèges.

## User Account Control (UAC)

Le contrôle du compte d'utilisateur (UAC) est une fonctionnalité de sécurité de Windows pour empêcher les logiciels malveillants d'exécuter ou de manipuler des processus qui pourraient endommager l'ordinateur ou son contenu. 

Il y a le mode d'approbation de l'administrateur dans UAC, qui est conçu pour empêcher l'installation de logiciels indésirables à l'insu de l'administrateur ou pour empêcher que des modifications ne soient apportées à l'échelle du système. Vous avez sûrement déjà vu l'invite de consentement si vous avez installé un logiciel spécifique, et votre système a demandé une confirmation si vous voulez qu'il soit installé. Étant donné que l'installation nécessite des droits d'administrateur, une fenêtre s'affiche, vous demandant si vous souhaitez confirmer l'installation. 

Avec un utilisateur standard qui n'a aucun droit pour l'installation, l'exécution sera refusée, ou on vous demandera le mot de passe de l'administrateur. Cette invite de consentement interrompt l'exécution de scripts ou de binaires que les logiciels malveillants ou les attaquants tentent d'exécuter jusqu'à ce que l'utilisateur entre le mot de passe ou confirme l'exécution.

## Registry 

Le registre est une base de données hiérarchique dans Windows critique pour le système d'exploitation. Il stocke les paramètres de bas niveau pour le système d'exploitation Windows et les applications qui choisissent de l'utiliser. 

Il est divisé en données spécifiques à l'ordinateur et en données spécifiques à l'utilisateur. Nous pouvons ouvrir l'éditeur de registre en tapant `regedit` à partir de la ligne de commande ou de la barre de recherche Windows.

L'ensemble du registre du système est stocké dans plusieurs fichiers sur le système d'exploitation. Vous pouvez les trouver sous `C:\Windows\System32\Config\`.


## Run and RunOnce Registry Keys

There are also so-called registry hives, which contain a logical group of keys, subkeys, and values to support software and files loaded into memory when the operating system is started or a user logs in. 

These hives are useful for maintaining access to the system. These are called Run and RunOnce registry keys..

## Application Whitelisting

Une liste blanche d'applications est une liste d'applications logicielles approuvées ou d'exécutables autorisés à être présents et à s'exécuter sur un système. L'objectif est de protéger l'environnement contre les logiciels malveillants nuisibles et les logiciels non approuvés qui ne correspondent pas aux besoins commerciaux spécifiques d'une organisation. La mise en œuvre d'une liste blanche forcée peut être un défi, en particulier dans un grand réseau. 

Une organisation devrait d'abord mettre en œuvre une liste blanche en mode audit pour s'assurer que toutes les applications nécessaires sont sur liste blanche et ne sont pas bloquées par une erreur d'omission, ce qui peut causer plus de problèmes qu'elle ne le résout.

AppLocker is Microsoft's application whitelisting solution and was first introduced in Windows 7. AppLocker gives system administrators control over which applications and files users can run. It gives granular control over executables, scripts, Windows installer files, DLLs, packaged apps, and packed app installers.

https://learn.microsoft.com/en-us/windows/security/application-security/application-control/windows-defender-application-control/applocker/applocker-overview

## Local Group Policy



## Windows Defender Antivirus


