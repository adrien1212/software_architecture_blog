+++
title = "Module"
weight = 50
+++

Comme pour un [Service]({{% ref "service.md" %}}) un module peut être vu à différente granularité (e.g. une classe, un package, etc ...). Il est donc difficile de donner une définition précise. La modularité est un principe d'organisation

## Définition

{{% notice style="warning" title=" " icon=" " %}}
La modularité consiste à décrire un regroupement logique de code (*related grouping of*)
{{% /notice %}}

Comme évoqué dans la section dédiée au [Découpage Physique/Logique]({{% ref "logical_physical_separation.md" %}}) du code nous préviligions un découpage logique de notre architecture.

Ainsi un module se définit par :
* encapsule du code et des données qui implémente une fonctionnalité particulire
* a une interface qui permet d’accéder à cette fonctionnalité de manière uniforme
* est facilement pluggable à un autre module
* est packagé comme une seule unité, donc facilement déployable


## Mesurer la modularité
La modularité d'un module peut se mesurer grâce à plusieurs métriques. Les deux principales sont :
- Le couplage : l'objectif est d'avoir des modules ayant un faible couplage entres eux
- La cohesion : les éléments regroupés au sein d'un même module doivent avoir une forte cohésion, ils couvrent les mêmes objectifs, la même fonctionnalité

> voir la section [Couplage et Cohesion]({{% ref "../characteristics/couplage_and_cohesion.md" %}})