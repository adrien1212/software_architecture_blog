+++
title = "Service"
weight = 40
+++

{{% notice style="tip" title="Ressource" icon="fa fa-book" %}}
- [Lesson 134 - What is a Service?](https://youtu.be/AHMlV_Y80Zw)
{{% /notice %}}

Tout au long des chapitres suivants nous allons parler de *Service*, regardons donc ensemble que signifie ce terme.

## Définition
{{% notice style="warning" title=" " icon=" " %}}
Un service est une unité déployable qui accomplit une activité métier ou d'infrastructure
{{% /notice %}}

![Service example](../images/service_example.png)

Dans l'exemple de la vidéo, nous obtenons :
- un service `Ticket` qui contient l'ensemble de règles de métiers. Un service est donc un regroupement logique de règles (qui sont des classes Modules, des classes Java, etc ...)
- mais ce même service peut être vu comme deux services distincts. Un premier qui assure la maintenance du ticket (sa création, sa réalisation, etc ...), un second qui s'occupe de l'acheminement des tickets.

Avec cette exemple, on voit que nos services peuvent être vus avec des granularités différentes.

## Caractérisiques par architecture 
Nous revenons sur les différents nom donnés à un service dans les [archiectures distribuées]({{% relref "../../architecture_style_distribued" %}})

### Microservices
> Le service se nomme un *microservice*

Caractéristisques :
- répond à un seul objectif (e.g. Service création de tickets)
- d'une granularité fine
- posséde leur propre base de données ([bounded context]({{% relref "../../architecture_style_distribued/microservices/bounded_context.md" %}}))
- communique fréquement avec les autres (micro)services

### Service-Based 
> Le service se nomme un *domain service*

Caractéristisques :
- contient plusieurs fonctionnalités métiers (e.g. le domaine ticket, le domaine facture, etc ...)
- d'une granularité gros grain
- tous les domain services partagent une même base de données
- communique rarement avec les autres (domain)services

### Event-Driven
> Le service se nomme un *event processor*

Caractéristisques :
- d'une granularité variante
- Déclenche et/ou répond à des évènements
- La communication entres les events processus se fait de manière asynchrone (via broker)
- peut posséder sa propre base de données ou avoir une base de données partagée


### Space-based
> Le service se nomme une *processing unit*

Caractéristisques :
- d'une granularité variante
- Contient un stockage de données in-memory
- La communication avec la base de données se fait de manière asynchrone
- Les services se up et se down fréquement ([élasticité]({{% relref "../../characteristics/elasticity.md" %}}) forte)