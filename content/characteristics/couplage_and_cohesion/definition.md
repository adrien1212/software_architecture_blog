+++
title = "Définition"
weight = 10
+++

{{% notice style="tip" title="Ressource" icon="fa fa-icon" %}}

- [(Fin de l'article) I don't love the single responsibility principle](https://sklivvz.com/posts/i-dont-love-the-single-responsibility-principle/)

{{% /notice %}}

## Couplage

{{% notice style="warning" title=" " icon=" " %}}
Coupling tells to which degree a change in one part of the system affects another. Usually we aim for loose coupling so that we can change things independently. But the decoupling may come with a burden, which forces us to make trade offs.
{{% /notice %}}

A est couplé à B, si pour créer/utiliser A nous devons nécessairement avoir créer B. En d'autres termes, le couplage est le nombre de connexions entre deux ou plusieurs unités (e.g. des classes, des modules, etc ...). Plus ce nombre est faible, plus le couplage est faible.

![couplage](../images/couplage.png)

```java
B b = new B()
A a = new A( b ) // A couplé à B
```

## Cohésion

{{% notice style="warning" title=" " icon=" " %}}
Cohesion tells whether code that changes for the same reason, is put closely. We aim for high cohesion.
{{% /notice %}}

La cohésion représente la mesure dans laquelle une partie d'un code (e.g. un ensemble de classe) constitue une unité logique. L'objetif est de regrouper les éléments partageant une même logique ensemble; ceci peut être des classes qu'on regroupe dans un même module/service, des fonctions qu'on regroupe dans une même classe, etc ...
