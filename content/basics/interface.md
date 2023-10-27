+++
title = 'Les interfaces'
date = 2023-10-27T18:26:00+02:00
weight = 10
+++

Une interface permet de définir un ensemble de services qu’un client peut obtenir d’un objet :
- Elle définit les méthodes (i.g. service) qui vont pouvoir être appelées
- Elle définit les informations que doit founir l'appelant (i.g paramètre de la méthode)
- Elle définit les informations que l'appelant va obtenir (i.g type de retour)
 
![Alt text](../images/interface.png)

Pour communiquer avec la `Appelée` la classe `Appelant` devra respecter le contrat éditer dans l'infterface `Interface`.
- `Appelant` devra fournir un objet de type `A` 
- `Appelant` recevra du service un objet de type `B`

## Changer l'implémentation
{{% notice info %}}
Une interface permet d'avoir un fort découplage entre l'appelant et l'appelée.
{{% /notice %}} 

![Alt text](../images/interface2.png)

Grâce à cette conception, si nous décidons de changer la classe `Appelée` par `Appelée2` l'appelant n'aura ni besoin d'être recompilé, ni besoin d'être redeployé car il a seulement connaissance de l'interface et pas l'implémentation concrète. L'abstraction permet d'exposer uniquement le service tout en cachant l'implémentation concrète.

