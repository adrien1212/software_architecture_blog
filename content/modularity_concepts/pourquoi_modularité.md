+++
title = "Pourquoi la modularité ?"
weight = 5
+++

{{% notice style="note" title=" " icon=" " %}}
La conception logique n'est qu'une pièce de la conception logicielle. L'autre pièce est la conception physique.
{{% /notice %}}

Lorsqu'on développe un logiciel on pense principalement à la _conception logique_ de notre code : relations entres classes, methodes d'une classe, packagement, etc ... Néanmoins il est également important de prendre en compte la _conception physique_ de notre application.

Avec conception physique on se demande :

- comment notre logiciel va être packagé en unité déployable
- Quelle classe va dans qu'elle unité
- Gérer les relation entre les unités
