+++
menuPre = " - 6.1 "
linkTitle = "Monolithiques"
title = "Architectures Monolithiques"
weight = 61
+++

{{% notice style="warning" title= " " icon=" " %}}
An architecture is monolithic when all the code is a single unit of deployment.
{{% /notice %}}

## Inconvénients généraux

- Déployabilité (faible) : L'ensemble de l'application ou du site web doit être déployé en une seule unité, ce qui rend les déploiements fréquents difficiles. Même le plus simple des changements nécessite une construction et un déploiement complets de l'ensemble de l'application.

- Tolérance aux pannes (faible) : Du à son caractère monolithique si une partie une de l'architecture provoque une erreur hors mémoire, l'ensemble de l'unité d'application est affectée et tombe en panne.

- Scalabilité (faible) : peu de choses peuvent être faites après le déploiement pour réagir à une augmentation de la charge.

- Élasticité (faible) : comme pour la scalibilité, ce style d'architecture ne peut pas répondre aux pics d'utilisation au-delà de sa capacité intégrée.
