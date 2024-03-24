# Gestion des conteneurs

La "conteneurisation", au même titre que les machiens virtuels permet des déployers des applications dans des environnements isolés. Docker, Docker compose et LXC (Linux container) sont des technologie permettant cela sur les systèmes Linux.

En terme de sécurité, les conteneurs sont isolé du système host mais également des autres conteneurs ce qui permet une isolation maximum et une surface d'attaque restreinte. Ceux-ci sont également extrément légés ce qui réduire d'autant plus la surface d'attaque. Il existe quand même des façon d'escalader les priviléges et de s'échaper du docker. 

D'un point de vue opérationnel, cela rend les applications beaucoup plus facile à déployer et à faire évoluer de façon efficiente et sécurisé.

## Docker

Docker est une plate-forme open source permettant d'automatiser le déploiement d'applications en tant qu'unités autonomes appelées conteneurs. Il utilise un système de fichiers en couches et des fonctionnalités d'isolement des ressources pour offrir flexibilité et portabilité. De plus, il fournit un ensemble robuste d'outils pour la création, le déploiement et la gestion des applications, ce qui aide à rationaliser le processus de conteneurisation.


Pour lancer un conteneur il faut récupérer une image depuis https://hub.docker.com. Celui-ci contient des images publique et privée créer et publier par la communauté ou par les équipes de docker directement.

La création d'une image docker commence par la création d'un "dockerfile" puis ensuite du "build" de cette image.

Pour finir, une fois l'image crée il suffit de faire un "docker run" de l'image pour démarrer le conteneur.

Il est important de noter que les conteneurs Docker sont conçus pour être immuables, ce qui signifie que toutes les modifications apportées à un conteneur pendant l'exécution sont perdues lorsque le conteneur est arrêté. Par conséquent, il est recommandé d'utiliser des outils d'orchestration de conteneurs tels que "Docker Compose" ou "Kubernetes" pour gérer et mettre à l'échelle les conteneurs dans un environnement de production.


## LXC (Linux Containers)

LXC et Docker sont tous deux des technologies de conteneurisation qui permettent d'emballer et d'exécuter des applications dans des environnements isolés. Cependant, il y a quelques différences entre les deux.


LXC est une technologie de virtualisation légère qui utilise les fonctionnalités d'isolement des ressources du noyau Linux pour fournir un environnement isolé pour les applications. Dans LXC, les images sont construites manuellement en créant un système de fichiers racine et en installant les paquets et configurations nécessaires. Ces conteneurs sont liés au système hôte, peuvent ne pas être facilement portables et peuvent nécessiter plus d'expertise technique pour les configurer et les gérer. LXC fournit également certaines fonctionnalités de sécurité, mais pas aussi robuste que Docker.

D'autre part, Docker est une plate-forme centrée sur les applications qui s'appuie sur LXC et fournit une interface plus conviviale pour la conteneurisation. Ses images sont construites à l'aide d'un Dockerfile, qui spécifie l'image de base et les étapes nécessaires à la construction de l'image. Ces images sont conçues pour être portables afin qu'elles puissent être facilement déplacées d'un environnement à un autre. Docker fournit une interface plus conviviale pour la conteneurisation, avec un riche ensemble d'outils et d'API pour la gestion et la configuration des conteneurs avec un environnement plus sécurisé pour l'exécution des applications.