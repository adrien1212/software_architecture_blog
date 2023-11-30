+++
title = "Définition"
weight = 10
+++

{{% notice style="warning" title=" " icon=" " %}}
La modularité consiste à décrire un regroupement logique de code (*related grouping of*). Ce regroupement devient une unité logicielle déployable, manageable, réutilisable, composable et stateless qui fournit une interface concise au client.
{{% /notice %}}

Comme évoqué dans la section dédiée au [Découpage Physique/Logique]({{% relref "../logical_physical_separation.md" %}}) du code nous préviligions un découpage logique de notre architecture.

Ainsi un module se définit par :
* encapsule du code et des données qui implémente une fonctionnalité particulire
* a une interface qui permet d’accéder à cette fonctionnalité de manière uniforme
* est facilement pluggable à un autre module
* est packagé comme une seule unité, donc facilement déployable


On peut également donner les caractéristique suivantes, un module est :
- déployable
- Managable
- Testatble
- Réutilisable
- composable
- Stateless


## Lien avec l'architecture logicielle
> L'architecture Logicielle à pour objectif de **minimiser l'impact et le coût du changement**. La modularité est un intermédiaire important pour augmenter l'agilité architecturalle. 
