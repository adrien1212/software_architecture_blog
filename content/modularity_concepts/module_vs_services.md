+++
title = "Modules VS Services"
weight = 60
+++

Depuis Java 9 nous pouvons créer des modules et j'ai souvent entendu des personnes dire que ces modules permettait de faire du microservices (puisque chaque module était indépendant). Ceci montre une incompréhension des réponses apportés par les modules et les services d'autres part.

## Le conditionnement

La **différence** entre un module et un service **réside dans le conditionnement**.

- Les modules sont des composants au niveau de la programmation qui encapsulent un morceau de logiciel pour qu'il soit réutilisé par d'autres logiciels via un _in-memory function calls_ (i.g. appel classique d’une fonction). Par exemple, une dépendance Maven.
- Un microservice est le déploiement d'un logiciel destiné à être utilisé par d'autres logiciels au travers d'un protocole (e.g. http); on parle donc de _out-of-process_.

![module vs service](../images/module_vs_service.png?width=40pc)

Comme on le voit ci-dessus :

- Les microservices peuvent être composés de modules (qui permettent de structure le code). Ces modules sont soient des fonctionnalités internes mais peuvent être également des dépendances externes (e.g. Junit et Log4j). Ces dépendances ne sont pas déployées sur un serveur, nous allons les utilisées en interne sans passer par un protocole (http) mais en faisant des appel classique de fonction
- D'un autre côté les microservices qui sont un niveau d'abstraction au dessus peuvent également se transmettre des données, mais au lieu d'avoir une dépendance nous préférons avoir un protocole standardisée permettant l'échange.

> Un module encapsule du code pour pouvoir être réutilisée au sein d'une application. Un microservice encapsule un besoin (sous forme de code) et offre ce service aux autres.
