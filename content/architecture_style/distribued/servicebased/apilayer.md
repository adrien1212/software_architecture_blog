+++
title = "Api Layer"
weight = 20
+++

Nous pouvons ajouter une couche "API Layer" qui va faire office de *reverse proxy* ou de *gateway* entre nos services et l'interface utilisateur.

![Alt text](../images/api_layer.png)

## Pourquoi l'utiliser ? 

L'avantage de cette pratique c'est qu'elle abstrait notre système derrière un "mur". Les systèmes externes communiquent avec nos services uniquement au travers de la couche API. Cette couche peut par exemple s'assurer que l'utilisateur ait le droit de consulter la ressource (authentification et autorisation). 
1. L'utilisateur envoie une requête au service de Commande
2. La couche API Layer contacte le service d'Authentification 
3. Le service d'authentification retourne une réponse autorisant ou non l'accès (e.g. vérifier si l'utilisateur saisi est le bon)
4. Si l'authentification est réussite avec la couche API Layer transmet à requête au service Commande. Dans le cas contraire, l'API Layer ne contacte pas le service et retourne un code d'erreur au client (e.g. mot de passe incorrect)


> On retrouve un fonctionnement similaire avec la librairie [Spring Cloud Gateway](https://spring.io/blog/2019/08/16/securing-services-with-spring-cloud-gateway)