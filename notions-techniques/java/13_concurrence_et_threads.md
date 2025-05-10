---
tags:
  - tutorials
  - java
---

# Concurrence et threads

La **concurrence** est la capacité d'un programme à **faire plusieurs choses en même temps**. Cela passe par ce qu'on appelle le **multithreading** : l'utilisation de plusieurs "**threads**", qui sont comme des mini-programmes dans un programme.

> 💡 **_Un exemple_** : dans un jeu vidéo, un personnage peut avancer tandis qu'un autre peut attaquer en même temps. Chaque action peut être gérée par un thread différent.

## Thread

Un **thread** est un **flux d'exécution** : on démarre un programme, Java crée un **thread principal** ("_main thread_") qui exécute la méthode `main()`. On peut ensuite créer d'autres threads pour gérer des actions en parallèle.

Les **threads** en Java sont des objets comme tous les autres objets Java : ils sont des instances de la casse `java.lang.Thread`, ou des instances de sous-classes de cette classe. Leur particularité est qu'ils peuent exécuter du code.

### Créer et démarrer un thread

Plusieurs méthodes permettent de créer des **threads** :

1. en étendant la classe `Thread` et en réécrivant sa méthode `run()` :

```java
public class DeplacerPersonnage extends Thread {
  public void run() {
    System.out.println("Le personnage se déplace ...");
  }
}

new DeplacerPersonnage().start(); // va permettre de faire démarrer le thread
```

2. en implémentant l'interface `Runnable` :

```java
public class Ennemi implements Runnable {
  public void run() {
    System.out.println("L'ennemi attaque !");
  }
}

Thread t = new Thread(new Ennemi());
t.start();  // va permettre de faire démarrer le thread
```

> ℹ️ Différence entre "étendre" et "implémenter" un thread :
>
> - lorsqu'on étend la classe `Thread`, on ne peut pas étendre une autre classe
> - en implémentant l'interface `Runnable`, on peut étendre à partir d'une autre classe
>
> On recommandera, en autres raisons, de prévilégier `implements Runnable`.

> ⚠️ Attenton à ne pas confondre `run()` ≠ `start()` :
>
> ```java
> new Thread(new Ennemi()).run(); // ❌ car ce n'est pas un nouveau thread
> new Thread(new Ennemi()).start(); // ✅ car démarre un nouveau thread
> ```

### Faire une pause dans un thread

Parfois, on veut **forcer l'attente** avant de continuer le thread. Si on garde l'exemple d'un jeu vidéo, on trouve généralement un délai avant de pouvoir utiliser une aciton à nouveau ("_cooldown_") :

```java
try {
  Thread.sleep(3000); // pause de 3 secondes
} catch (InterruptedException e) {
  e.printStackTrace()
}
```

### Arrêter proprement un thread

Un **thread** est aussi soumis aux erreurs, et donc aux crashs. Idéalement, en les ayant évité ou catchés, on voudra **arrêter** un thread soi-même. Il faut alors penser à une condition d'arrêt, comme par exemple avec une boucl `while`.

### Problèmes de concurrences

Étant donné que les threads s'exécutent en même temps que d'autres parties du programme, il n'existe aucun moyen de savoir dans quel ordre le code s'exécutera. Quand les threads et le programme principal lisent et écrivent les mêmes variables, les valeurs sont imprévisibiles, voire se perdent :

```java
public class Main extends Thread {
  public static int pointsDeVie = 100; // variable partagée

  public static void main(String[] args) {
    Main thread = new Main();   // création d’un thread
    thread.start();             // démarrage du thread ; exécute la méthode run() en parallèle

    System.out.println(pointsDeVie); // A
    pointsDeVie--;                  // B : décrémente la variable
    System.out.println(pointsDeVie); // C
  }

  public void run() {
    pointsDeVie--; // D : exécutée par le thread en parallèle
  }
}
```

↳ **le résultat est imprévisible** :
Les instructions dans `main()` (lignes A, B, C) et l'instruction dans `run()` (ligne D) s'exécutent en parallèle. Cela signifie qu'**on ne sait pas exactement quand le thread exécutera** la ligne `pointsDeVie--` par rapport aux autres lignes dans `main()`. Et surtout : la variable `pointsDeVie` est **partagée**, mais pas protégée contre un accès concurrent.

> 👉 Les résultat possibles seraient :
>
> ```shell
> 100
> 99
> ```
>
> Ou aussi :
>
> ```shell
> 99
> 98
> ```
>
> Et d'autres ... donc des résultats instables !

> 💡 Pour éviter les problèmes de concurrences, on peut partager le moins d'attributs possible entre les threads. Si néanmoins certains doivent être partagés, une solution possible consiste à utiliser une méthode (nommée `isAlive()` par convention) pour vérifier si le thread a terminé son exécution ou non.

```java
public class Main extends Thread {
  public static int pointsDeVie = 100;

  public static void main(String[] args) {
    Main thread = new Main();
    thread.start();

    // on attend que le thread soit terminé
    while(thread.isAlive()) {
      System.out.println("Thread en cours ...");
    }

    // puis on update les valeurs
    System.out.println(pointsDeVie);
    pointsDeVie--;
    System.out.println(pointsDeVie);
  }

  public void run() {
    pointsDeVie--;
  }
}
```

## Synchronisation

Un autre manière d'éviter les problèmes de concurrences est d'utiliser une **synchronisation**. Il s'agit d'un mot-clé qui permet de **verrouiller un bloc de code** ou une méthode : pendant qu'un thread exécute le code, **aucun autre thread ne peut y entrer**.

```java
public class Main extends Thread {
  public static int pointsDeVie = 100;

  public static void main(String[] args) {
    Main thread = new Main();
    thread.start();

    afficherEtModifier();
  }

  public static synchronized void afficherEtModifier() {
    System.out.println(pointsDeVie);
    pointsDeVie--;
    System.out.println(pointsDeVie);
  }

  public synchronized void run() {
    pointsDeVie--;
  }
}
```

↳ ici, `pointsDeVie` **est partagé** entre le thread principal et le thread secondaire (`run()`). On synchronise donc `afficheEtModifier()` et `run()`, et grâce à `synchronized`, **seulement un thread à la fois peut modifier** `pointsDeVie` ; l'autre attend que le premier ait fini.

---

## Exercices

Les exercices [13_concurrence_et_threads](https://github.com/association-z-code-emploi/exercices-java/tree/main/13_concurrence_et_threads) sont recommandés pour pratiquer les notions vues durant ce cours.
