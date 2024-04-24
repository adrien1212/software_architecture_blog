+++
title = "Niveau Système"
weight = 2
+++

{{% notice style="tip" title="Ressource" icon="fa fa-icon" %}}

- [https://youtu.be/w9a7eI6BlVc?t=1677](https://youtu.be/w9a7eI6BlVc?t=1677)
  {{% /notice %}}

Nous changeons notre niveau d'abstraction et allons regarder comment faire en sorte que notre architecture (nos systèmes (e.g. des services) ) soient faiblement couplée.

## Event-driven architecture
Une approche par *Messages & Évènements* est souvent utilisé pour rendre nos systèmes faiblement couplés. Elle consiste à un ensemble de *producers* qui transmette des évènements sous la forme d'un message à des *consumers* qui les traitent.

On peut affirmer que notre architecture est très peu couplée car les *consumers* ne connaissent pas les *producers* et vice-versa.