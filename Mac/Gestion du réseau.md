# Gestion du réseau

## Gestion des interfaces 

* GUI : Depuis réglages > Réseau
* CLI : Via ifconfig ou networksetup


Remarque : 

Les modifications apportées avec `ifconfig` sont temporaires et seront écrasées par le gestionnaire de service réseau après un redémarrage. Pour que les modifications soient persistantes, assurez-vous d'utiliser le NetworkManager dans l'interface graphique ou via la commande `networksetup`.

## VPN

* OpenVPN : Gratuit et Open Source
* Tunnelblick : Gratuit et Open Source, fonctionne avec OpenVPN
* Viscosity : Payant

## Bonjour 

Nous ne pouvons pas parler de macOS et de la mise en réseau sans mentionner rapidement Bonjour. Bonjour est l'implémentation open-source d'Apple du réseau sans configuration. Il permet la découverte automatique de périphériques et de services sur un réseau à l'aide de protocoles IP, de la gestion de l'adressage, de la dénomination des appareils et de la découverte de services sur les réseaux. Les appareils comme les imprimantes, les téléviseurs, les périphériques multimédias en continu et même d'autres applications qui permettent le partage de médias et d'autres actions quotidiennes utilisent maintenant cette norme sous une forme ou une autre.

Du point de vue de l'administrateur, c'est génial car cela nous permettra de sauter une tonne de configuration manuelle nécessaire pour configurer des appareils tels que des imprimantes dans un environnement d'entreprise. Mais du point de vue de la sécurité, cela pourrait causer des problèmes.

Dans macOS, nos hôtes utilisent un protocole appelé mDNSResponder pour effectuer les actions de découverte de services pour utiliser Bonjour et sa suite de services. Grâce à lui, nos hôtes peuvent automatiquement découvrir et potentiellement accéder à d'autres hôtes et périphériques macOS exécutant la suite de protocoles. Cela signifie que tout hôte de notre réseau capable d'utiliser mDNS ou Bonjour peut accéder aux hôtes ou à d'autres services auxquels il n'a peut-être pas eu accès. Dans cet esprit, c'est une bonne idée de vous assurer que vous utilisez une certaine forme de sécurité réseau/appareil ainsi que la segmentation du réseau et les mécanismes d'authentification dans votre environnement.