# Design pattern "factory method"

Ce design pattern indique comment créer des classes chargés de l'instanciation des objets.

Pour plus d'informations sur ce design pattern veuillez consulter la page disponible [ici](https://www.baeldung.com/java-factory-pattern#factory-method-pattern)

## Exercice d'application

L'objectif est ici de mettre en place le design pattern "factory method" pour l'instanciation de plusieurs types de pizzas :
- Margherita ;
- Pepperoni ;
- vg ;
- Ananas
- ...

Chaque pizza peut être modélisée par une classe. Cette classe pourra contenir une méthode `prepare()` détaillant la recette.

Voici un exemple de code qui peut être utilisé pour implémenter les classes pizzas :

```java
/**
 * Classe abstraite correspondant à la pizza MERE de toutes les pizza !
 */
public abstract class Pizza {
    public abstract void prepare();
}
```

```java
/**
 * Classe concrète pour la Margherita !
 */
public class MargheritaPizza extends Pizza {
    @Override
    public void prepare() {
        System.out.println("Tomates, mozza', basilic. Que demander de plus ?");
    }
}
```

## Travail à faire

1. En vous aidant d'un exemple de code de "factory method", établir le diagramme de classe UML permettant de représenter votre solution pour mettre en place une "factory" pour les pizzas.
2. Implémenter les classes constituant la factory
3. Tester le logiciel via des appels à partir de la fonction `main` et/ou des tests unitaires