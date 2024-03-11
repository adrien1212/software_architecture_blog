+++
title = "Service"
weight = 40
+++

{{% notice style="tip" title="Ressource" icon="fa fa-book" %}}

- [Lesson 134 - What is a Service?](https://youtu.be/AHMlV_Y80Zw)
  {{% /notice %}}

Tout au long des chapitres suivants nous allons parler de _Service_, regardons donc ensemble que signifie ce terme.

## Définition

{{% notice style="warning" title=" " icon=" " %}}
Un service est une unité déployable qui accomplit une activité métier ou d'infrastructure
{{% /notice %}}

![Service example](../images/service_example.png)

Dans l'exemple de la vidéo, nous obtenons :

- un service `Ticket` qui contient l'ensemble de règles de métiers. Un service est donc un regroupement logique de règles (qui sont des classes Modules, des classes Java, etc ...)
- mais ce même service peut être vu comme deux services distincts. Un premier qui assure la maintenance du ticket (sa création, sa réalisation, etc ...), un second qui s'occupe de l'acheminement des tickets.

Avec cette exemple, on voit que nos services peuvent être vus avec des granularités différentes.

### Bibliothèque VS Service

[https://martinfowler.com/articles/microservices.html#ComponentizationViaServices](https://martinfowler.com/articles/microservices.html#ComponentizationViaServices)

Nous définissons les bibliothèques comme des composants liés à un programme et appelés à l'aide _in-memory function calls_ (i.g. appel classique d'une fonction), tandis que les services sont des composants _out-of-process_ qui communiquent avec un mécanisme tel qu'une demande de service web (http) ou un appel de procédure à distance (remote).

### Service as composant

L'une des principales raisons d'utiliser les services comme composants (plutôt que comme bibliothèques) est que les services peuvent être déployés indépendamment les uns des autres. Si vous avez une application qui consiste en plusieurs bibliothèques dans un processus unique, une modification de l'un des composants entraîne le redéploiement de l'ensemble de l'application. En revanche, si cette application est décomposée en plusieurs services, on peut s'attendre à ce que de nombreuses modifications apportées à un seul service n'entraînent qu'un redéploiement de ce dernier.

## Caractérisiques par architecture

Nous revenons sur les différents nom donnés à un service dans les [archiectures distribuées]({{% relref "../../architecture_style_distribued" %}})

### Microservices

> Le service se nomme un _microservice_

Caractéristisques :

- répond à un seul objectif (e.g. Service création de tickets)
- d'une granularité fine
- posséde leur propre base de données ([bounded context]({{% relref "bounded_context" %}}))
- communique fréquement avec les autres (micro)services

### Service-Based

> Le service se nomme un _domain service_

Caractéristisques :

- contient plusieurs fonctionnalités métiers (e.g. le domaine ticket, le domaine facture, etc ...)
- d'une granularité gros grain
- tous les domain services partagent une même base de données
- communique rarement avec les autres (domain)services

### Event-Driven

> Le service se nomme un _event processor_

Caractéristisques :

- d'une granularité variante
- Déclenche et/ou répond à des évènements
- La communication entres les events processus se fait de manière asynchrone (via broker)
- peut posséder sa propre base de données ou avoir une base de données partagée

### Space-based

> Le service se nomme une _processing unit_

Caractéristisques :

- d'une granularité variante
- Contient un stockage de données in-memory
- La communication avec la base de données se fait de manière asynchrone
- Les services se up et se down fréquement ([élasticité]({{% relref "../../characteristics/elasticity.md" %}}) forte)
