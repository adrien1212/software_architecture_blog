+++
title = "Layered Avancée"
weight = 10
+++

Pour éviter qu'une requête traverse toutes les couches, nous appliquons de l'inversion de dépendances entre nos couches.

![Alt text](../images/n-tiers-detailled.png)

## Interface de contrat
Chaque couche définie son contrat au travers d'interfaces. 
1. Le Controller envoie une requête au service dont le contrat d'échange est `A`
2. Le Service doit transformer cette requête pour respecter le contrat d'échange avec le repository qui est `B`

![Alt text](../images/ntiers-dto.png)

En d'autre terme :
- `A` est le DTO de requête (car il peut y a voir un DTO de réponse) entre la *présentation* et la *business logic*. Le contrôler doit envoyer ses données sous le format `A`
- `B` est le DTO de requête (car il peut y a voir un DTO de réponse) entre la *business logic* et la *persistance* Le Service doit envoyer ses données sous le format `B`