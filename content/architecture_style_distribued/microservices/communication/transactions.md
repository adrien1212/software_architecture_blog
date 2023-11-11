+++
title = "Transactions"
weight = 20
+++

Là où l'atomicité est un principe trivial en architecture monolithique il devient compliqué de le mettre en place dans un architecture distribuée en microservices. En effet, avec l'architecture microservices nous souhaitons un découplage fort, mais comment doit-on assurer les transactions qui se déroulent au sein de plusieurs services ?

## Revoir la granularité (Boundaries)
Etant donnée que la gestion des transactions entre plusieurs services est difficile, la première solution consiste à revoir la granularité de nos composants. Comme nous l'avons dans la section dédiée au [Bounded Context]({{% ref "../bounded_context.md" %}}) les transactions *boundaries* sont l'un des indicateurs courants de la granularité des services.

> Don’t do transactions in microservices—fix granularity instead!

## SAGA
{{% notice style="tip" title= "Ressources" icon="fa fa-book" %}}
- [https://microservices.io/patterns/data/saga.html](https://microservices.io/patterns/data/saga.html)
{{% /notice %}} 

Mais il arrive que nos services ont vraiment des architectures différentes et que les frontières soient bien délimité. Dans ce cas, des patterns existe comme SAGA.

Le patron SAGE permet de gérer les transactions en utilisant une séquence de transactions locales de microservices. Chaque microservice possède sa propre base de données et peut gérer les transactions locales de manière atomique avec une cohérence stricte.

Ce patron peut être utilisé à la fois avec une *Choreography-based* et avec une *Orchestration-based* (voir [ressources](https://microservices.io/patterns/data/saga.html))

Ici nous nous concentrons sur l'explication théorique de son fonctionement. 
1) Le service `médiateur`iateur reçoit une requête
2) Il effectue une requpete vers le service `CreditCardWaller`
3) Qui lui retourne une réponse pour signifier que la demande est *enregistrée*
4) Le service `médiateur` envoie également une requête vers le service `CustomerProfile`
5) Mais une **erreur se produit**
6) Le service `médiateur` rollback donc la demande *enregistrée* en 3) pour revenir à un état stable
7) L'utilisateur est informé d'une erreur

Si à l'étape 5) nous aurions eu un succès de l'étape, alors les demandes *enregistrées* auraient été *commit*

![SAGA](../images/SAGA.png?width=35pc)