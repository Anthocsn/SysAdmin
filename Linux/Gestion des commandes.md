# Gestion des commandes

## Executer des commandes à la suite.

Pour cela il existe 3 façons de faire :

* ; : Permet d'enchainer des commandes indépendaments du résultat de la commande précédente.
* && : Permet Permet d'enchainer les commandes uniquement si le resultat de la commande précédent ne retourne pas d'erreur.
* | : Dans le cas du pipe il faut à la fois que la commande précédente n'est pas d'erreur mais la commande d'après dépendra du résulat de la précédente.