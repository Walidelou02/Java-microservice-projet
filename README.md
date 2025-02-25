# Java-microservice-projet
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

![Configuration prise du depôt de github](images/githubParameter.png)

Ici on voit le parametre à récupérer par le ConfigServer dans github.

![Controlleur de microservice-commande](images/ControllerGithubParameterAndFunctionUsingIt.png)

Ici on remarque que la configuration faite dans le github est injecte dans l attribut puis dans l'action qui du controlleur qui permet de consulter les dernier commandes selon un nombre de jours passé en paramétre

![Résultat de l'action getRecentCommandes de microservice-commande](images/ResultOfUseCase1.png)

Ici on remarque que la communication avec ConfigServer et Github et notre microservice a bien passé et on a recu les objets qui aboutissent à la logique du code

### Eureka et api-gateway et Produit et Commandes

1) Pour bien lancer l'application il faut d'abord lancer le EurekaServer puis api-gateway et finalement les deux microservices

![Résultat de l'action getRecentCommandes de microservice-commande](images/les ports.png)

2) Maintenant on peut consulter le Eureka Server qui va nous donner la liste de nos microservice

![Résultat de l'action getRecentCommandes de microservice-commande](images/eurekaScreen.png)

3) Donc apres avoir vu la liste des microservice qui sont UP on peut maintenant appeler notre endpoint du microservice commande qui permet de communiquer avec le microservice produit tous en passant via l api gateway

![Résultat de l'action getRecentCommandes de microservice-commande](images/apiGateWayAndCommands.png)

4) On peut bien apercevoir que notre endpoint est activé via l'api gateway

5) Maintenant essayons de passer par l api gateway vers commande vers produit
   il faut qu' on atteint cette endpoint du controlleur du microservice commande qui va communiquer avec le microservice produit 

![communicationWithOtherMicroserviceEndpoint.png](images%2FcommunicationWithOtherMicroserviceEndpoint.png)


le microservice produit est defini comme ceci :
![Résultat de l'action getRecentCommandes de microservice-commande](images/explication.png)


6) finalement on obtient un resultat comme cela :
   ![Résultat de l'action getRecentCommandes de microservice-commande](images/result.png)

