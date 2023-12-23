+++
title = "Définition modularité"
weight = 10
+++

{{% notice style="warning" title=" " icon=" " %}}
La modularité consiste à décrire un regroupement logique de code (_related grouping of_). Ce regroupement devient une unité logicielle déployable, manageable, réutilisable, composable et sans état (stateless) qui fournit une interface concise au client.
{{% /notice %}}

![Module](../images/module.png?width=40pc)

Un module est donc une pièce logiciel qui

- encapsule du code et des données pour effectuer une fonctionnalité
- a une interface qui permet d’accéder à cette fonctionnalité de manière uniforme
- est facilement pluggable à un autre module
- est packagé comme une seule unité, donc facilement déployable

## Caractéristiques

On peut également donner les caractéristique suivantes pour un module. Il est :

- Déployable
- Managable
- Testable
- Réutilisable
- Composable
- Stateless

## Lien avec l'architecture logicielle

> L'architecture Logicielle à pour objectif de **minimiser l'impact et le coût du changement**. La modularité est un intermédiaire important pour augmenter l'agilité architecturalle.
