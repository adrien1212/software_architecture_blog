+++
title = "Architectures Distribuées"
weight = 10
+++


## Avantages
- Résilience : si un service tombe les autres non
- Scalabilité : e.g. netflix pique vers 20h
- Agilité : des équipes plus autonomes; on va pouvoir cloisoner les équipes, chacune travaille sur ce microservice => on évite le code spaguehtti
Et les équipes n'ont pas besoin d'utiliser le même langage ni les même techniques, on expose juste nos services via interface

## Inconvéniant
Mais un système distribué a également de nombreux désavantages
- Compliqué à mettre en place
- Compliqué à monitorer
- Il faut une équipe dédié pour maintenir l'architecture et le réseaux
- Le cout est très élevé. E.g. Prime Video sont passés du microservice au monolith pour réduire leur cout de 90%
100 ms => alors 200 réplicat (2 par ms) => un monolithique coute moins cher 