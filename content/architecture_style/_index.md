+++
archetype = "chapter"
menuPre = "5. "
title = "Styles Architecturaux"
weight = 5
+++

> Nous définissons un style d'architecture comme la structure globale entre de l'interface utilisateur et le backend (e.g. layered architecture avec déploiement monolithique) et la manière dont le code interagit avec la base de données.

L'objectif de l'architecte débutant est de comprendre les différents styles et les compromis qu'ils impliquent. 

## Classification
Les styles d'architecture peuvent être classés en deux types principaux : *monolithique* (une seule unité de déploiement de tout le code) et *distribué* (plusieurs unités de déploiement connectées par des protocoles d'accès à distance). 

Monolithique :
- Layered architecture
- Pipeline architecture
- Microkernel architecture

Distribuée
- Service-based architectur
- Event-driven architecture
- Space-based architecture
- Service-oriented architectur
- Microservices architecture

{{% notice info %}}
Les architectures distribuées partagent toutes un ensemble commun de défis et de problèmes que l'on ne retrouve pas dans les styles d'architecture monolithique
{{% /notice %}} 
