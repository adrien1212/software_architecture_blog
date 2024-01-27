+++
title = "Organiser son code"
weight = 30
+++

{{% notice style="tip" title="Ressource" icon="fa fa-icon" %}}

- [https://enterprisecraftsmanship.com/posts/cohesion-coupling-difference/](https://enterprisecraftsmanship.com/posts/cohesion-coupling-difference/)
- [Domain Layer Structure & Skeleton | Clean Architecture & DDD From Scratch Tutorial](https://youtu.be/jnutb5Z4wyg)
  {{% /notice %}}

Au lieu de packager son application par utilisation (entity, service, repository) il est préférable de l'organisation par logique métier.

![Poorly Boundaries](../images/poorly_boundaries.png?width=15pc&classes=inline)

![Btter Boundaries](../images/better_boundaries.png?width=15pc&classes=inline)

La cohesion de chaque module est maintenant maximale et le couplage entre les 3 modules (order, products et users) est faible.
