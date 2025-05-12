# Design pattern "singleton

## Principe

Le design pattern Singleton permet de s'assurer qu'une classe ne puisse produire qu'une **seule et unique instance**. 

Pour plus d'informations sur ce design pattern veuillez consulter la page disponible [ici](https://refactoring.guru/design-patterns/singleton).

## Exercice d'application

L'objectif est de centraliser la gestion des mots de passes d'une application dans un **unique objet centralisé**.

Il vous est demandé de créer une classe `PasswordVault` respectant le pattern singleton.

Cette classe devra permettre de :
- ajouter un mot de passe pour la connexion à un service via la méthode `addPassword(String service, String password)`
- récupérer un mot de passe à partir d'un nom de service via la méthode `getPassword(String service)`

> [!WARNING]
> Pour des raison de commodité de développement les mots de passe ne seront ni chiffrés, ni hashés.

> [!TIP]
> Pour stocker les mots de passe vous pouvez utiliser un objet de la classe `HashMap<String, String>`. Plus d'informations [ici](https://www.ionos.fr/digitalguide/sites-internet/developpement-web/java-hashmap/)
>
> Veillez bien à ce que le constructeur de `PasswordVault` soit **privé**.

## Travail à faire

1. Etablir le diagramme de classe UML permettant de représenter vptre solution
2. Implémenter la classe `PasswordVault`
3. Tester votre classe via des appels à partir de la fonction `main` et/ou des tests unitaires

> [!WARNING]
> Vérifiez bien à ce que plusieurs appels de la méthode `getInstance` renvoient bien une seule et même instance.
> L'identifiant unique d'un objet peut, par exemple, être récupéré en utilisant la méthode statique `Objects.toIdentityString(...)`. Documentation disponible [ici](https://howtodoinjava.com/java/object-identity-string/#2-accessing-the-object-identity-string)