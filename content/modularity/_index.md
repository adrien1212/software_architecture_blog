+++
menuPre = "5. "
archetype = "chapter"
title = "Modularité"
weight = 50
addBrBefore = true
+++

{{% notice style="tip" title="Ressource" icon="fa fa-book" %}}

- [Java Application Architecture: Modularity Patterns with Examples Using OSGi](https://www.oreilly.com/library/view/java-application-architecture/9780132874779/)
- [18 Modularity Patterns (pdf)](/pdf/18-modularity-patterns.pdf)
  {{% /notice %}}

Les notions de _module_ et de _modularité_ viennent compléter la définition d'un [Service]({{% relref "service.md" %}}). Les principes pour la conception de services peuvent être appliqués pour la conception de modules.

Dans cette section, nous donnerons la définition d'un module en nous basant sur le livre _Java Application Architecture_ puis nous verrons comment les principes de Module et de Service sont fortement liés.

## Point clé
> The crucial aspect of modularity is concept of 'interchangeability'. If you can replace one component of your design with another component without changing anything else, we can say there is a high degree of modularity with that aspect of the design.

## Mesurer la modularité

La modularité d'un module peut se mesurer grâce à plusieurs métriques. Les deux principales sont :

- Le couplage : l'objectif est d'avoir des modules ayant un faible couplage entre eux
- La cohesion : les éléments regroupés au sein d'un même module doivent avoir une forte cohésion, ils couvrent les mêmes objectifs, la même fonctionnalité

Un module avec très peu de comportement ne sera pas utile s'il n'est pas couplé à d'autres modules. De même un module trop conséquent sera trop sur à réutiliser dans un autre contexte. Ainsi quand on conçoit un module la difficulté est de trouver la bonne granularité.

> voir la section [Couplage et Cohesion]({{% relref "../../characteristics/couplage_and_cohesion/" %}})
