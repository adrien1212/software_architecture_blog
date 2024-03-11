+++
title = "Communication"
weight = 30
+++

Le choix du bon style de communication aide les équipes à maintenir les services découplés tout en les coordonnant de manière appropriée.

De manière générale, les architectes doivent choisir entre une communication synchrone ou asynchrone.

- synchrone : l'appelant doit attendre la réponse de l'appelé
- asynchrone : utilisation d'événements et de messages (e.g. Event Driven Architecture). Les notions de _Brokers_ et de _Mediateur_ correspondent respectivement à la _Chorégraphie_ et à l'_Orchestration_ en microservices
