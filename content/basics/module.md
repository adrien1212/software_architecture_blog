+++
title = "Module"
weight = 50
+++

Comme pour un [Service]({{% ref "service.md" %}}) un module peut être vu à différente granularité. Il est donc difficile de donner une définition précise. La modularité est un principe d'organisation

## Définition

{{% notice style="warning" title=" " icon=" " %}}
La modularité consiste à décrire un regroupement logique de code (*related grouping of*)
{{% /notice %}}

Les classes, les packages sont des séparations physiques, pas logiques. Une séparation logique ça se construit en ayant une interface sans dépendances externes. Un module :
- encapsule du code et des données qui implémente une fonctionnalité particulire
- a une interface qui permet d'accéder à cette fonctionnalité de manière uniforme
- est facilement pluggable à un autre module 
- est packagé comme une seule unité, donc facilement déployable


## Mesurer la modularité
Ref coupling, cohésion