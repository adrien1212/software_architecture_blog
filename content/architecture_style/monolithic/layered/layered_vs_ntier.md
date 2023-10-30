+++
title = "Layered VS N-tiered"
weight = 20
+++

Presque toutes les personnes dans le monde du logiciel utilisent ces deux termes de manière interchangeable, comme s'il s'agissait exactement de la même chose. Néanmois on peut noter une différence notable.

## N-tiered
Correspond à une division physique du système et de comment le code tourne (e.g client et serveur). 
Lorsqu'on parle d'architecture 3-tiers on fait donc référence à une sépration physique.

![tiers](https://librecours.net/module/culture/langages-du-web/pres/res/servers.png?width=30pc)

Si votre logiciel est stocké sur un serveur, il s'agit d'une architecture 1-tier. Si votre logiciel est stocké sur deux serveurs :
- un premier qui est responsable de la couche (layer) présentation
- un second qui est responsable de la partie backed (couche business, couche accès à la base de données)

Vous avez donc une architecture 2-tiers, où chaque tier peut gérer plusieurs couches.

## Layered
Correspond à une division logique du sytème. Les couches typiques sont la présentation, le business et les données.

![layered](https://www.oreilly.com/api/v2/epubs/9781491971437/files/assets/sapr_0101.png?width=30pc)


## Relation N-tiered et Layered
Dans un système simple, on retrouve les trois mêmes couches 
- 3-tiers : séparation physique - présentation, business, base de données
- 3-layers : sépration logique - présentation, business, base de données

Néanmois, comme vu dans l'exemple précédent, un tier peut contenir plusieurs couches (layers)