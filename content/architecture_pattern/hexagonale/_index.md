+++
title = "Architecture Haxagonale"
weight = 10
+++

> Elle vise à créer des systèmes à base de composants d'application qui sont faiblement couplés et qui peuvent être facilement connectés à leur environnement logiciel au moyen de ports et d'adaptateurs (wikipédia)

On souhaite éviter les dépendances entre les couches. 

## Construction
### 1. Le coeur applicatif 

Le coeur applicatif contient l'ensemble de la logique métier est totalement indépendant de la *présentation* ou de la *persistance*.

![Alt text](images/hexa1.png?width=15pc)

### 2. Communication sortante
Néanmoins notre application a besoin de communiquer avec plusieurs librairie : base de données, email, etc ...
Au lieu d'avoir une dépendance directe avec ce module tier, on va utiliser un port/adaptateur.

![Alt text](images/hexa2.png?width=30pc)

- Le port permet aux classes métier de communiquer avec l'extérieur sans la base de données. Tout passe au travers d'un contrat.
- L'adaptateur est la logique qui permet d'effectuer l'écriture en base de donnée.
- Par conséquent, les données envoyées par les classes métier sont converties par l'adaptateur en une donnée lisible pour la base de données.

![Alt text](images/hexa3.png?width=40pc)

> Et quelque soit les changements effectués, seul l'adaptateur changera. Le coeur applicatif, lui, reste inchangé. On découple la logique interne avec l'utilisation de modules tiers.

### 3. Communication entrante

On peut faire de même pour les communications entrantes, par exemple lorsque notre logique métier est appelée par une API.
Pour ce faire, on va définir un contrat d'échange où on préciser comment on souhaite recevoir les données (interface + DTO de requête) et quelles données nous renvoyons (DTO de réponse). Par conséquent, quelque soit l'appelant l'input et l'ouput seront toujours les mêmes.

```java
interface IService {
    /* L'appelant devra fournir un RequestDTO et obtiendra un ResponseDTO */
    ResponseDTO methode(RequestDTO requestDTO);
}
```

![Alt text](images/hexa4.png)

> Nous n'avons plus besoin de passer du temps à déterminer à quoi devrait ressembler tel ou tel DTO, et quelles sont les données dont le frontend besoin. Nous pouvons plutôt nous concentrer sur les données que nous voulons exposer au frontend. 

Dans notre cas les données qu'on souhaitera exposer au frontend seront les attributs contenus dans `ResponseDTO`