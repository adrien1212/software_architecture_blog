+++
title = "Niveaux architecturaux"
weight = 30
+++

{{% notice style="tip" title="Ressources" icon="fa fa-book" %}}
- [What's the difference between Architectural Patterns and Architectural Styles?](https://stackoverflow.com/questions/3958316/whats-the-difference-between-architectural-patterns-and-architectural-styles)
- [Contrasting architecture patterns with design patterns - O'Reilly](https://www.oreilly.com/radar/contrasting-architecture-patterns-with-design-patterns/)
{{% /notice %}} 


Tout est question de champ d'application :
- Un [style architectural]({{% relref "architectural_styles.md" %}}) est la conception de l'application au niveau d'abstraction le plus élevé ;
- Un [patron architectural]({{% relref "architectural_patterns.md" %}}) est un moyen d'implémenter un style architectural ;
- Un [patron de conception]({{% relref "design_patterns.md" %}}) est un moyen de résoudre un problème localisé.

Dans l'ensemble de ce cours nous nous concentrerons sur les [styles architecturaux]({{% relref "architectural_styles.md" %}}) tout en évoquant très brièvement les [patrons architecturaux]({{% relref "architectural_patterns.md" %}}) mais nous ne reviendrons pas sur les [patrons de conception]({{% relref "design_patterns.md" %}}). Nous reviendrons seulements sur certains concepts fondamentaux nécessaire pour comprendre les niveaux supérieurs.


{{% notice style="info" %}}
Certaine architecture apparraisent à la fois comme un style architectural et un patron architectural. C'est le cas du *microservices*, wiképédia le considère comme un patron tandis que dans le livre Software Architecture Pattern les deux termes sont employés sans distinction pour décrire cette architecture.  
Ainsi, ici on ne se prendra pas la tête que ce soit un style ou un patron s'il est intéressant de l'étudier nous le ferons.
{{% /notice %}}