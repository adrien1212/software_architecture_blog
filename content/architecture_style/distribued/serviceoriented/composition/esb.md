+++
title = "Enterprise Service Bus"
weight = 10
+++

Notre SI est composé de plusieurs services qui ne sont pas écrit dans un même langage, qui n'utilisent pas les mêmes protocoles. Nous devons trouver un moyen d'assurer la communication entre notre différents services. 

## Définition

{{% notice style="warning" title= " " icon=" " %}}
Un ESB fournit des capacités de communication et de transformation à travers une interface de service réutilisable. Vous pouvez considérer un ESB comme un service centralisé qui achemine les demandes de service vers le service approprié. 
{{% /notice %}} 


Un Enterprise Service Bus (ESB) est un composant central qui se positionnera comme un interlocuteur unique pour tous les composants du SI. Ainsi, quand vous voudrez appeler un composant X, vous n'irez plus jamais lui parler directement. Vous ne saurez même pas quel protocole il accepte, ni son URL ! Il suffira d'envoyer une requête (e.g. SOAP) à l'ESB qui lui s'occupera ensuite de faire le nécessaire pour transformer votre message et l'adapter avant de le transférer au composant demandé. Il fera ensuite la même chose pour la réponse.

Avec une connexion point-à-point les différents services auraient du adapter leur message pour chaque service intérrogé. Maintenant avec un ESB qui centralise tous les adaptateurs nous n'avons besoin de connecter nos services à l'ESB qui se charge de traduire la requête puis la réponse.
 
![ESB](https://it.ucla.edu/sites/default/files/media/images/esb_diagrams_1b.jpg)