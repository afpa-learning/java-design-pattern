# Design pattern "façade"

## Principe

Le design pattern Façade fournit une interface simplifiée à un ensemble de classes ou à un sous-système complexe.

Pour plus d'informations sur ce design pattern veuillez consulter la page disponible [ici](https://refactoring.guru/fr/design-patterns/facade).

## Exercice d'application

Créer une application qui simule le fonctionnement d’un jukebox composé de plusieurs sous-systèmes (lecteur, amplificateur, haut-parleur), en utilisant une façade pour simplifier son utilisation.

Les différentes classes internes du système sont les suivantes :
- `AudioPlayer` : le lecteur audio
- `Amplifier` : l'amplificateur du signal audio
- `Speaker` : les hauts parleurs du système

Voici le code de ces différentes classes :

```java
/**
 * Classe qui simule le sous-système de lecture de musique du jukebox 
 */
public class AudioPlayer {
    /**
     * Méthode de chargement d'une piste
     */
    public void load(String track) {
        System.out.println("Loading track: " + track);
    }

    /**
    * Lance la lecture de d'une piste
    */ 
    public void play() {
        System.out.println("Playing audio...");
    }
}

/**
 * Classe simulant la partie amplification du jukebox
 */
public class Amplifier {
    /**
     * Démarre l'amplificateur
     */
    public void turnOn() {
        System.out.println("Amplifier on");
    }

    /**
     * Règle le volume de l'amplificateur
     * Volume min : 1
     * Volume max : 10
     */
    public void setVolume(int level) {
        System.out.println("Setting volume to: " + level);
    }
}

/**
 * Classe qui simule les hauts-parleur
 */
public class Speaker {
    /**
     * Connecte les hauts-parleur au système de son principal
     */
    public void connect() {
        System.out.println("Speaker connected");
    }

    /**
     * Emet le signal audio
     */
    public void outputSound() {
        System.out.println("Sound outputting...");
    }
}
```

Voici l'algorithme à suivre pour simuler le démarrage d'une piste audio :
1. activation de l'amplificateur
2. réglage du volume de l'amplificateur (par défaut à 5)
3. connexion des hauts-parleurs
4. chargement du nom de la piste dans le lecteur
5. démarrage de la lecture de la piste
6. déclencement du son des hauts-parleurs

Cet algorithme fait appel à plusieurs méthodes des différentes classes détaillées ci-dessous. L'intérêt du patron de conception est de cacher cette logique pouvant être complexe dans une méthode d'une autre classe.

Ainsi, la classe `JukeboxFacade` peut être créée.
Elle devra comprendre :
- 3 **attributs privés** correspondants à 3 objets `AudioPlayer`, `Amplifier` et `Speaker`
- un **constructeur public** permettant d'instancier les 3 objets
- une méthode **playMusic(String track)** permettant de déclencher la lecture d'une piste

## Travail à faire

1. Etablir le diagramme de classe UML permettant de représenter le système complet
2. Implémentez la classe `JukeboxFacade` correspondant à la classe qui devra être appelée pour démarrer une piste audio.
3. Tester votre classe via des appels à partir de la fonction `main` et/ou des tests unitaires