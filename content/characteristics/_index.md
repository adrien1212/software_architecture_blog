+++
archetype = "chapter"
title = "4. Caractéristiques Archi."
weight = 4
+++

Le terme *Caractéristiques Architecturales* englobe les notions de :
- [Critères non-fonctionnel](https://en.wikipedia.org/wiki/Non-functional_requirement)
- [Quality attributes](https://en.wikipedia.org/wiki/List_of_system_quality_attributes)

Il n'existe pas une liste standart, néanmoins l'ISO à publié une [liste organisée par catérogie](https://iso25000.com/index.php/en/iso-25000-standards/iso-25010) 

![Iso 25010](https://iso25000.com/images/figures/en/iso25010.png)

Un logiciel ne peut pas appliquer toutes ses caractérisiques, il faudra faire des compromis :
- Chaque caractéristiqueque demande des efforts
- Chaque caractéristique architecturale peut en impacter une autre. Augmenter la *Sécurité* fera diminuer la *Performance* du système.

Il faudra alors prendre le temps d'identifier les caractéristique architecturale important du métier

![Translation of domain concerns to architecture characteristics](images/domain_concern.png)