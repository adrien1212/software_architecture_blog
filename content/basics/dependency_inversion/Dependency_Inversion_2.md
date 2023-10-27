+++
title = 'Inversion de dépendances (2)'
date = 2023-10-27T18:26:00+02:00
weight = 20
+++

Dans la partie précendente nous avons défini le notion d'intersion de dépendances. Dans cette seconde partie, nous l'améliorons.

## Retour sur la partie 1
Dans la figure de gauche, nous avons un module de bas niveau qui défini une API (via un interface) et un module de haut niveau qui intéragie avec le module de bas niveau au travers de cette API.

Dans la figure de droite, nous avons chageons le propriétaire du contrat. C'est maintenant c'est le module de haut niveau qui définit les fonctionnalités qui sont requises par chaque implémentation de cette interface.

Ainsi le module de haut niveau défini une abstraction où :
- Le module de haut niveau dépend de cette abstraction
- Le module de bas niveau dépend aussi de cette abstraction (implémentation)

![Alt text](../../images/DI2-1.png)

## Améliorer l'inversion de dépendance
Etant donné que le module de bas niveau implémente le module de haut niveau il est impossible de réutiliser le module de bas niveau dans un autre contexte, par exemple dans une autre application. Pour résoudre ce problème nous utilisons de patron de conception *Adaptateur*.

![Alt text](../../images/DI2-2.png)

1. Nous créons une interface dans le module de bas niveau. Par conséquent, les deux modules peuvent maintenant être réutilisés dans n'importe quel contexte.
2. Nous créons une nouvelle classe *Adapter* que nous positionnons dans un module tier. 
    - L'adaptateur implémente l'interface du module de haut niveau
    - L'adaptateur utilise l'interface du module de bas niveau
    - L'adaptateur permet aussi de convertir les structuteurs de données entre les deux modules.


## Conclusion
- Le module de haut niveau est indépendant des détails.  
- Le module de bas niveau peut être réutilisé dans différent contexte.
- Les informations convertie sont transmisses au travers de DTOs


Ressource:  
[https://youtu.be/-3Z9L6sIAMM](https://youtu.be/-3Z9L6sIAMM)