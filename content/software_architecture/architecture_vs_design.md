+++
title = "Architecture VS Design"
weight = 3
+++

{{% notice style="tip" title="Ressources" icon="fa fa-book" %}}
- [Lesson 167 - Architecture vs Design](https://youtu.be/0tEBv2kAuNY)
- [https://stackoverflow.com/questions/704855/software-design-vs-software-architecture](https://stackoverflow.com/questions/704855/software-design-vs-software-architecture)
{{% /notice %}} 


Dans cette section nous étudierons la différence entre l'Architecture Logicielle (*Software Architecture*) et la Conception Logicielle (*Software Design*).
Il est important  de bien comprendre Les responsabilités d'un architecte celles d'un développeur ? 

> Penser comme un architecte, c'est connaître la différence entre l'architecture et la conception et comprendre comment les deux s'intègrent étroitement pour former des solutions.

## Définition
Wikipédia nous donne les premiers [élément de réponse](https://en.wikipedia.org/wiki/Architecture_description_language#Architecture_vs._design)

{{% notice style="warning" title=" " icon=" " %}}
La Conception Logicielle (*Software Design*) s'intéresse à l'implémentation concrète du code et à la mise en oeuvre des bonnes pratiques de programmation.
{{% /notice %}}

{{% notice style="warning" title=" " icon=" " %}}
L'Architecture Logicielle (*Software Architecture*) est un dégrès plus haut. On s'intéresse au partitionnement des grandes fonctionnalités, nous analysons les besoins métiers afin de s'assurer que les choix techniques vont pouvoir y répondre (extension, maintenance, performance, fiabilité, etc).
{{% /notice %}}

### Architecture Logicielle
L'objectif de l'Architecture Logicielle est de déterminer quel est le meilleur moyen de répondre aux besoins métiers. Elle répond au *quoi?*. On va déterminer les systèmes de stockage, la communication entres modules, les systèmes de récupération. On fait également des choix de technologie qui sont en adéquation avec les exigences techniques du client (maintenance, evolutilité, fiabilité, performance, etc ...).

On se concentre sur la stratégie à adopter. On va s'aider de patrons architecturaux (n-tiers, event-based, microservices, etc) pour répondre besoins fonctionels et non-fonctionnels du client.

### Conception Logicielle
L'objectif de la Conception Logicielle est d'implémenter les exigences fonctionelles. Elle répond au *comment?*. Cette conception permet de se concentrer sur le fonctionnement interne de chaque module (e.g. classe Java), leur rôle et comment il va communiquer avec les autres modules. Elle nous aide à produire un code de bonne qualité en se basant sur les principes SOLID, les Design Patterns, etc ...

On se concentre sur l'implémentation concrète d'une architecture. Par exemple, nous regardons comment nous allons implémenter la logique métier `m` en utilisant l'Architecture Hexagonale.

## D'après Mark Richards et Neal Ford
![Alt text](../images/architecture_vs_design.png)

Comme le montre le diagramme, l'architecte est responsable de la mise en œuvre du projet. L'analyse des besoins de l'entreprise, extraire et de définir les caractéristiques  architecturales, Délectionner les modèles et styles d'architecture qui conviendraient et créer les composants du système. **Mais** avec cette vision l'architecte est déconnecté des équipes de développement et, de ce fait, l'architecture fournit rarement ce pour quoi elle a été conçue à l'origine. 

![Alt text](../images/architecture_vs_design2.png)

Le barrière virtuelle doit être supprimée et l'équipe doit être composée à la fois de l'architecte et des développeurs. Ce modèle facilite une communication bidirectionnelle forte entre l'architecture et le développement, il permet également à l'architecte d'assurer le mentorat et le coaching des développeurs de l'équipe.

>  Une collaboration étroite entre l'architecte et l'équipe de développement est essentielle à la réussite de tout projet logiciel. Mais où s'arrête l'architecture et où commence la
commence la conception ? Nul part. Elles font toutes deux partie du cycle de vie d'un projet logiciel et doivent toujours être synchronisées.

## Conclusion
**Architecture Logicielle**
- *Quoi?* faire pour répondre au besoin client
- *Pourquoi?* faire ce choix
- Se concentre sur les choix stratégiques
- Language, framework, périmètre, méthodologie de travail, etc 

**Conception Logicielle**
- Complète l'Architecture Logicelle avec le *Comment?* implémenter
- Se concentre sur les contraintes locales 
- Design Patterns, SOLID, etc ...