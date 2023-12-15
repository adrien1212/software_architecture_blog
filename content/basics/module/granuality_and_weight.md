+++
title = "Granularité et Poids"
weight = 20
+++

Dans cette section nous abordons les notions de *Granualarité* et de *Poids* d'un module
Ces définitions sont également valable pour des autres composants (e.g. services, classes Java)

## Granularité
{{% notice style="warning" title="Définition" icon=" " %}}
La modularité est la mesure dans laquelle un module est décomposé en plusieurs parties
{{% /notice %}}

Les modules gros grains (*coarse-grained*) ont tendance a avoir un comportement plus riche (il font plus de chose) que les modules à grains fins (*fine-grained*). Pour maximiser la réutilisation on essaie de composé des coarsed-grained module en utilisant des fine-grained modules. Mais ceci entraine beaucoup de dépendances entres les modules à grains fins. On notera également que gérer le déploiement d'un seul gros module est plus simple que le déploiement de plusieurs petits modules.

{{% notice style="note" title=" " icon=" " %}}
Coarse-grained modules sont plus facilement utilisables, mais les fine-grained modules sont plus facilement réutilisables
{{% /notice %}}

## Poids
{{% notice style="warning" title="Définition" icon=" " %}}
La modularité est la mesure dans laquelle un module dépend de son environnement
{{% /notice %}}

Un module poids lourd (*heavyweight*) dépend de son environnement opérationnel, tandis qu'un module poids léger (*lightweight*) évite ces dépendances. La question se pose donc d'embarquer les dépendances liés à l'OS par exemple à l'intérieur du module (donc en faire un heavyweight module) ou de gérer les dépendances liés à l'OS lors du déploiement du module.

{{% notice style="note" title=" " icon=" " %}}
Heavyweight modules sont plus facilement utilisables, mais les lightweight modules sont plus facilement réutilisables
{{% /notice %}}

On retrouve également un compromis à faire. Si nous créons un coarse-grained module basé sur 4 fine-grained modules. Si chacun de ces modules n'a besoin que d'un seul applicatif et OS pour fonctionner on peut encapsuler tous les code de l'environnement dans module. On obtient ainsi 4 fine-grained/heavyweight modules.
A contrario, si nous souhaitons réutiliser ces modules sur différents environnements nous devons placer le code de configuration des environnement en dehors des modules et s'assurer qu'il peut être configurer à la volé suivant l'environnement, on obtient donc 4 fine-grained/lightweight modules.


## Compromis
La granualarité et le poids sont des considérations importantes dans la conception de modules. Il faut trouver le bon équilibre
- Coarse-grained et Heavyweight modules sont plus facilement *utilisables*
- File-grained et Lightweight modules sont plus facilement *réutilisables*
