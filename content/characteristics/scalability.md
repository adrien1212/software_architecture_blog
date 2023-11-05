+++
title = "Scalabilité"
weight = 10
+++

{{% notice style="tip" title="Ressource" icon="fa fa-book" %}}
- [https://stackoverflow.com/questions/9420014/what-does-scalability-mean](https://stackoverflow.com/questions/9420014/what-does-scalability-mean)
- [https://itrexgroup.com/blog/what-is-software-scalability/](https://itrexgroup.com/blog/what-is-software-scalability/)
{{% /notice %}}

D'après wikipédia, 

{{% notice style="warning" title=" " icon=" " %}}
La scalabilité est la capacité d'un système à subvenir aux besoins en ressources, sans prendre en compte la rapidité, le temps, la fréquence, ni la granularité de ses actions lorsque le nombre d'utilisateur augmente
{{% /notice %}}

La *scalabilité* consiste à gérer un grand nombre d'utilisateur sans avoir une dégradation sérieuse des performence. Il peut s'agir, d'un nombre de requêtes plus important, d'une plus grande quantité de données (data-set) à traiter, etc ...

La *scalabilité* correspond donc à la capacité du système à faire face à des charges plus importantes en ajoutant des ressources :
- soit en ajoutant des nœuds supplémentaires (scale out)
- soit en renforçant le matériel (scale up)

## Scale out (horizontale)
Vous pouvez *scaler* un logiciel horizontalement en incorporant des nœuds supplémentaires dans le système pour gérer une charge plus importante.
![hozitontal scalability](../images/scalability1.png)

## Scale up (verticale)
Le *scale* verticale consiste à ajouter de la puissance au matériel existant. Il s'agit ici d'updrade le serveur existant en y ajoutant de la puissance de traitement, de la mémoire, etc.

![hozitontal scalability](../images/scalability2.png)