+++
title = 'Data Transfer Object'
date = 2023-10-27T18:26:00+02:00
weight = 30
+++

## Définition
{{% notice style="warning" title=" " icon=" " %}}
A Data Transfer Object (DTO) is an object that is used to encapsulate data, and send it from one subsystem of an application to another.
{{% /notice %}}

Il permet de transformer des informations qui transfère entre deux couches. Par exemple, dans l'exemple suivant le `AccountService` attend des objets de type `AccountRequestModel`.
Ainsi, le Contrôleur :
- Recupère les informations fournies par l'utilisateur (e.g. identifiant utilisateur, nom du compte, etc ...).
- Au lieu de transférer directement les informations au Service métier, il va les encapsuler dans un objet DTO.
- Transmet de DTO au Service métier

![Alt text](../images/dto.png)

## Un peu de code
```java
public interface AccountService {
    public create(AccountRequestModel accountRM);
}
```

```java
public class AccountRequestModel {
    private Long idCustomer;
    private Long idAccount;
    private String name;
    private String accountType;
}
```

Maintenant quand le contrôleur va recevoir les données il devra créer un `AccountRequestModel` et seulement après appeler le service. Néanmois pour diminuer le nombre de DTOs dans le système il est envisagble que la méthode `create()` prend en paramètre le même DTO (la vue et le contrôleur ont le même *request dto*).
```java
@PostMapping()
public void create(@RequestBody AccountRequestModel requestModel) {
    accountService.create(requestModel);
}
```

Le client doit ainsi envoyer un json correspondant à un `AccountRequestModel`, le contrôleur le transmettra ensuite au service
```json
{
    idCustomer: 1,
    idAccount: 4,
    name: "adrien"
    accountType: "CREDIT"
}
```
## ResponseModel (DTO de réponse)
{{% notice info %}}
Nous nous concentrons sur les données que nous voulons exposer au frontend. 
{{% /notice %}} 

En effet, nous ne souhaitons pas forcément exposer l'ensemble des informations de notre service. Ainsi on retourne un `AccountResponseDTO` qui contient des attributs correspondant à ceux qu'on souhaite réellement exposer au frontend 