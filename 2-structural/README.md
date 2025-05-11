# Design pattern "façade"

## Principe

Pour plus d'informations sur ce design pattern veuillez consulter la page disponible [ici](https://refactoring.guru/fr/design-patterns/facade).


## Exercice d'application

Créer une application qui simule le fonctionnement d’un jukebox composé de plusieurs sous-systèmes (lecteur, amplificateur, haut-parleur), en utilisant une façade pour simplifier son utilisation.

Les différentes classes internes du système sont les suivantes :
- `AudioPlayer` : le lecteur audio
- `Amplifier` : l'amplificateur du signal audio
- `Speaker` : les hauts parleurs du système

Voici le code de ces différentes classes :

```java
public class AudioPlayer {
    public void load(String track) {
        System.out.println("Loading track: " + track);
    }

    public void play() {
        System.out.println("Playing audio...");
    }
}

public class Amplifier {
    public void turnOn() {
        System.out.println("Amplifier on");
    }

    public void setVolume(int level) {
        System.out.println("Setting volume to: " + level);
    }
}

public class Speaker {
    public void connect() {
        System.out.println("Speaker connected");
    }

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

La classe `JukeboxFacade` doit être créée. Elle devra comprendre :
- 3 **attributs privés** correspondants à 3 objets `AudioPlayer`, `Amplifier` et `Speaker`
- un **constructeur public** permettant d'instancier les 3 objets
- une méthode **playMusic(String track)** permettant de déclencher la lecture d'une piste

## Travail à faire

1. Etablir le diagramme de classe UML permettant de représenter le système complet
2. Implémentez la classe `JukeboxFacade` correspondant à la classe qui devra être appelée pour démarrer une piste audio.