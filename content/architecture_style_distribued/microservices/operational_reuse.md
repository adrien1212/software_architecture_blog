+++
title = "Réutilisation"
weight = 20
+++

## Dupplication
{{% notice style="warning" title= " " icon=" " %}}
Avec l'architecture microservices on préfèrera dupliquer plutôt que coupler
{{% /notice %}} 

Avec une architecture monolithique il est commun de partager un composant (e.g. la classe `Adresse`) entre des partie disparates de l'application. Etant donnée qu'avec l'architecture microservices on essaie d'éviter le couplage nous préfèrerons dupliquer le composant dupliquer.

## Réutilisation
Cependant certain composant ont une rèelle valeur ajoutée uniquement lorsque nous réalisons un couplage. C'est le cas d'un système de *Logging* (logs) ou un *Circuit Breaker*.
De plus pour ces composants nous pouvons nous demander si nous préférions que chaque équipe en soit responsable ou avoir une organisation plus globale avec une équipe d'infrastructure.

### Sidecar pattern
Le composant sidecar gère toutes les questions opérationnelles que les équipes ont intérêt à coupler. Ainsi, lorsque le moment est venu de mettre à jour l'outil, l'équipe chargée de l'infrastructure peut mettre à jour le sidecar, et chaque microservice bénéficie de la nouvelle fonctionnalité.

![Sidecar](../images/sidecar.png)