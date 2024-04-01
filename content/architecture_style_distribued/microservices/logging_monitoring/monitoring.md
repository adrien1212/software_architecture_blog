+++
title = "Monitoring"
weight = 1
+++

## Implémenter le Logging

{{% notice style="warning" title= " " icon=" " %}}
Le Monitoring regarde les métriques et détecte les anomalies
{{% /notice %}}

Cela permet de fournir une vue simplifiée du systèmes. Par exemple Kibana propose la vue suivante

![kibana](../images/kibana.png?width=40pc)

## Deux types de monitoring

Il existe deux type de monitoring :

- infrastructure monitoring
- application monitoring

### Infrastructure monitoring

{{% notice style="warning" title= " " icon=" " %}}
On y contrôle le serveur (CPU, RAM, Disque, Réseau)
{{% /notice %}}

On alerte lorsqu'un problème d'infrastructure est détecté.

### Application monitoring

{{% notice style="warning" title= " " icon=" " %}}
On y contrôle l'application elle-même (Requêtes par minutes, commandes par jours, etc ...)
{{% /notice %}}

On alerte quand un problème applicatif est détecté.

## Les outils

Comme pour le Logging il existe plusieurs produit pour le Monitoring :

- Nagios
- Stack
- New Relic
- Application Insights
