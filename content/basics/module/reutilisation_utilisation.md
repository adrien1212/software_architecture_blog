+++
title = "Utilisation/Réutilisation Paradoxe"
weight = 30
+++

{{% notice style="warning" title=" " icon=" " %}}
L'objectif est de trouver le bon compromi entre la facilité d'utilisation d'un module et sa facilité à être utilisé dans une application tierce.
{{% /notice %}}

## Fine-grained/Lightweight module
Le fait de viser des modules Fine-grained/Lightweight permet d'avoir
- des modules facilement réutilisables
- une compréhension du système simplifié

Mais si nous sommes trop fin et trop léger
- nous obtenons une explosition du nombre de module et donc de dépendances inter-modules
- donc un énorme travail de configuration inter-module
- et plus nous avons de dépendances plus nos modules deviennent complexes et difficilement utilisables
- donc un changement dans un module peut impacter plusieurs autres modules

{{% notice style="note" title=" " icon=" " %}}
Maximiser la réutilisation complique l'utilisation
{{% /notice %}}

## Coarse-grained/Heavyweight module

Le fait de viser des modules Coarse-grained/Heavyweight permet :
- de diminuer le nombre de dépendances inter-modules
- de maintenir le changement dans un seul module
- la configuration ne se fait que à un seul endroit

Mais en contre-partie
- nous diminuons la réutilisation de notre module
- il peut fournir plus que nécessaire au client
- et il devient plus compliqué à comprendre et l'impact d'un changement peut être difficile à analyser

## Conclusion
La clé est de trouver le bon équilibre dans la tension utilisation/réutilisation.