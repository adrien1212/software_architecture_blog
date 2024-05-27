+++
title = "Niveaux architecturaux"
weight = 30
+++

{{% notice style="tip" title="Ressources" icon="fa fa-book" %}}

- [What's the difference between Architectural Patterns and Architectural Styles?](https://stackoverflow.com/questions/3958316/whats-the-difference-between-architectural-patterns-and-architectural-styles)
- [Architecture Styles VS Architecture Patterns - Mark Richards](https://youtu.be/I-yBv72RCeA?t=30)

- [Contrasting architecture patterns with design patterns - O'Reilly](https://www.oreilly.com/radar/contrasting-architecture-patterns-with-design-patterns/)
  {{% /notice %}}

Tout est question de champ d'application :

- Un [style architectural]({{% relref "architectural_styles.md" %}}) est la conception de l'application au niveau d'abstraction le plus élevé ;
- Un [patron architectural]({{% relref "architectural_patterns.md" %}}) est un moyen d'implémenter un style architectural ;
- Un [patron de conception]({{% relref "design_patterns.md" %}}) est un moyen de résoudre un problème localisé.

Dans l'ensemble de ce cours nous nous concentrerons sur les [styles architecturaux]({{% relref "architectural_styles.md" %}}) tout en évoquant très brièvement les [patrons architecturaux]({{% relref "architectural_patterns.md" %}}) mais nous ne reviendrons pas sur les [patrons de conception]({{% relref "design_patterns.md" %}}). Nous reviendrons seulement sur certains concepts fondamentaux nécessaire pour comprendre les niveaux supérieurs.

## Styles vs Patterns
> How does microservices differ from CQRS ?

Nous reprenons les dires de Mark Richards 
|                                          Styles Architecturaux                                         |                                                Patrons Architecturaux                                               |
|:------------------------------------------------------------------------------------------------------:|:-------------------------------------------------------------------------------------------------------------------:|
| Forment l’architecture globale de l’ensemble du Système                                                | Peut-être utilisé à avec n’importe quel style  architectural; ils permettent de résoudre un problème en particulier |
| Va influencer des aspects de la structure du Système (e.g. la communication, granularité des services) | Ne va pas influencer la structure globale du Système                                                                |                                                                         |

![styles vs patterns](images/styles_vs_patterns.png)

Par exemple la patron *circuit breaker* peut être mis en oeuvre avec n'importe quel style architectural