+++
archetype = "chapter"
menuPre = "6. "
title = "Styles Architecturaux"
weight = 60
addBrBefore = true
+++

{{% notice style="tip" title="Ressource" icon="fa fa-icon" %}}

- [https://betterprogramming.pub/trade-offs-on-monolithic-vs-distributed-architectures-7a04f86d47ad](https://betterprogramming.pub/trade-offs-on-monolithic-vs-distributed-architectures-7a04f86d47ad)
  {{% /notice %}}

> Nous définissons un style d'architecture comme la structure globale entre de l'interface utilisateur et le backend (e.g. layered architecture avec déploiement monolithique) et la manière dont le code interagit avec la base de données.

L'objectif de l'architecte débutant est de comprendre les différents styles et les compromis qu'ils impliquent.

## Classification

Les styles d'architecture peuvent être classés en deux types principaux : _monolithique_ (une seule unité de déploiement de tout le code) et _distribué_ (plusieurs unités de déploiement connectées par des protocoles d'accès à distance).

### Monolithique

{{% notice style="warning" title= " " icon=" " %}}
An architecture is monolithic when all the code is a single unit of deployment.
{{% /notice %}}

- Layered architecture
- Pipeline architecture
- Microkernel architecture

### Distribuée

{{% notice style="warning" title= " " icon=" " %}}
A distributed architecture is a group of deployment units connected through remote access protocols.
{{% /notice %}}

- Service-based architectur
- Event-driven architecture
- Space-based architecture
- Service-oriented architecture
- Microservices architecture

{{% notice info %}}
Les architectures distribuées partagent toutes un ensemble commun de défis et de problèmes que l'on ne retrouve pas dans les styles d'architecture monolithique
{{% /notice %}}
