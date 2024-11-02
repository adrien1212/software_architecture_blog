+++
title = "Niveau Système"
weight = 2
+++

{{% notice style="tip" title="Ressource" icon="fa fa-icon" %}}

- [I Made Everything Loosely Coupled - Event-driven architecture](https://youtu.be/w9a7eI6BlVc?t=1677)
  {{% /notice %}}

Nous changeons notre niveau d'abstraction et allons regarder comment faire en sorte que notre architecture (nos systèmes (e.g. des services) ) soient faiblement couplée.

## Low coupling, High cohésion niveau service

- Quand les services sont faiblement couplés alors un changement dans un service ne doit pas impacter les autres services
- Quand les services ont une forte cohésion alors les changement de comportement liés doivent se faire à un seul endroit

Nous devons donc concevoir nos services pour qu'ils puissent être modifiés et déployés de manière indépendante. En d'autres termes le bounded context de chaque service doit être correctement définie et les services communiquent via des interfaces (e.g. API REST) 

## Approches

### Organiser par feature
{{% notice style="tip" title="Ressources" icon="book" %}}
- [Package by feature, not layer](http://www.javapractices.com/topic/TopicAction.do?Id=205)
{{% /notice %}}

On va retrouver le même principe que dans la page précédente. On ne pas organiser notre code en différents projet (Presentation, Service et Persistance) mais en créant des projets représentant nos domaine métier (Client, Article) et dans ces dossiers un redécoupage en couche via les package.

### Event-driven architecture
Une approche par *Messages & Évènements* est souvent utilisé pour rendre nos systèmes faiblement couplés. Elle consiste à un ensemble de *producers* qui transmette des évènements sous la forme d'un message à des *consumers* qui les traitent.

On peut affirmer que notre architecture est très peu couplée car les *consumers* ne connaissent pas les *producers* et vice-versa.