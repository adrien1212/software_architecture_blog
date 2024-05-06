+++
title = "Transactions"
weight = 10
+++

Là où l'atomicité est un principe trivial en architecture monolithique il devient compliqué de le mettre en place dans un architecture distribuée en microservices. En effet, avec l'architecture microservices nous souhaitons un découplage fort, mais comment doit-on assurer les transactions qui se déroulent au sein de plusieurs services ?

## Revoir la granularité (Boundaries)

Etant donnée que la gestion des transactions entre plusieurs services est difficile, la première solution consiste à revoir la granularité de nos composants. Comme nous l'avons dans la section dédiée au [Bounded Context]({{% relref "../../../basics_for_modeling/bounded_context" %}}) les transactions _boundaries_ sont l'un des indicateurs courants de la granularité des services.

> Don’t do transactions in microservices — fix granularity instead!

## Le problème

Regardons néanmoins qu'elles sont les problèmes posées par les transactions dans un architecture distribuée :

- ACID : une transaction doit répondre aux caractérisitiques ACID. Dans un scénario de transaction distribuée, comme la transaction s'étend sur plusieurs services, il faut toujours garantir l'ACID.
- Niveau d'isolation : si un objet dans l'un des microservices est persisté dans la base de données
  alors qu'une autre requête lit les données, le service doit-il renvoyer les anciennes ou les nouvelles données ?

Des solutions existent pour assurer les transaction distribuées :

- Le Two-Phase Commit protocol (2PC) qui est un patron largement utilisé. Mais, il pose plusieurs problèmes
- Le SAGA est une deuxième stratégie qui repose sur des **transactions locales**. Par conséquent, chaque transaction locale (effectuée sur un microservice) peut être rollback si la transaction locale effectuée sur un autre microservice echoue.

> Par conséquent, le modèle Saga garantit que toutes les opérations se terminent avec succès ou que des transactions de rollback soient exécutées pour annuler le travail effectué précédemment.

## SAGA

{{% notice style="tip" title= "Ressources" icon="fa fa-book" %}}

- [https://microservices.io/patterns/data/saga.html](https://microservices.io/patterns/data/saga.html)
- [https://www.baeldung.com/cs/saga-pattern-microservices](https://www.baeldung.com/cs/saga-pattern-microservices)
  {{% /notice %}}

Le patron SAGE permet de gérer les transactions en utilisant une séquence de transactions locales de microservices. Chaque microservice possède sa propre base de données et peut gérer les transactions locales de manière atomique avec une cohérence stricte.

Ce patron peut être implémenenté à la fois avec une _Choreography-based_ et avec une _Orchestration-based_ (voir [ressources](https://microservices.io/patterns/data/saga.html))

Ici nous nous concentrons sur l'explication théorique de son fonctionement.

1. Le service `médiateur`iateur reçoit une requête
2. Il effectue une requpete vers le service `CreditCardWaller`
3. Qui lui retourne une réponse pour signifier que la demande est _enregistrée_
4. Le service `médiateur` envoie également une requête vers le service `CustomerProfile`
5. Mais une **erreur se produit**
6. Le service `médiateur` rollback donc la demande _enregistrée_ en 3) pour revenir à un état stable
7. L'utilisateur est informé d'une erreur

Si à l'étape 5) nous aurions eu un succès de l'étape, alors les demandes _enregistrées_ auraient été _commit_

![SAGA](../images/SAGA.png?width=35pc)
