# Projet microservice java

Ce projet est un exemple simple démontrant comment on peut faire une architecture microservice qui permet de communiquer un ensemble de microservice entre eux.
. Nous allons explorer la structure de base de notre projet ainsi que l'intégration visuelle via des captures d'écran.

---

## Table des Matières
1. [Explication](#introduction)
2. [Fonctionnalités](#fonctionnalités)

---

## Explication

Bienvenue dans **JAVA MICROSERVICE**. Ce projet est conçu pour savoir comment peut on communiquer un ensemble de microservice entre eux ansi l'utilistaion du dépot de github pour une configuration centralisé.

-Le microservice ConfigServer et microservice-commande communique entre eux de facon que le microservice-commande prends une valeur ou bien si on veut dire sa configuration du microservice ConfigServer qui permet
de charger en lui meme le fichier de configuration pose dans github dans ce lien :
https://github.com/Walidelou02/config-repo
Donc ce qui se passe le microservice-commande lors de son chargement il prends l'ensemble des clé valeurs enregistré dans le depot du git grâce au miroservice ConfigServer.
On a aussi utiliser une configuration à chaud c-a-d si jamais un changement se passe sur le depot du git qui contient la configuration on a pas besoin de redemarrer notre service
cela est fait grâce à l'actuator

-Les microservices  api-gateway, eureka-server, microservice-commande-etudeCas2, microservice-produits-etudeCas2 communique tous entre eux
de facon a ce que le eureka server permet de superviser tous ces microservice (api-gateway, microservice-commande-etudeCas2, microservice-produits-etudeCas2)
il permet de voir le port de configuration de chaque service ansi que son status.
l'api gateway permet de jouer le rôle d'une interface qui permet d'utiliser les deux microservices avec le meme port de l api gateway ce qui facilite la gestion et l'utilisation des microservices

---

## Installation

1. Clonez le dépôt :
   ```
   git clone https://github.com/Walidelou02/Java-microservice-projet/tree/master
   ```

---

## Fonctionnalités
-Pour tester la communication entre microservice-commande et ConfigServer il faut etre connecte à internet puis lancé premierement le ConfigServer puis microservice-commande

-Pour tester la communication entre les autres microservices il faut :
1) Lancer le eureka-server
2) Lancer api-gateway
3) microservice-commande-etudeCas2
4) microservice-produits-etudeCas2

### ConfigServer et microservice-commande
Voici des captures d'écran illustrant cette communication :

![Configuration prise du depôt de github]([https://via.placeholder.com/800x400.png?text=Page+d%27accueil](https://github.com/Walidelou02/Java-microservice-projet/blob/master/images/githubParameter.png))

![Page d'accueil](https://via.placeholder.com/800x400.png?text=Page+d%27accueil)

![Page d'accueil](https://via.placeholder.com/800x400.png?text=Page+d%27accueil)
### Exemple 2 : Formulaire d'Inscription
Un aperçu du formulaire d'inscription utilisateur :

![Formulaire d'inscription](https://via.placeholder.com/800x400.png?text=Formulaire+d%27inscription)



