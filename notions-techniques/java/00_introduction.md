---
tags:
  - tutorials
  - java
---

# Introduction à Java

Java est un langage de programmation orienté objet, conçu pour être portable (ie. vers d'autres systèmes), sécurisé et solide. Il est utilisé dans :

- le développement d'applications web et mobiles
- la programmation embarquée et les objets connectés
- les applications d'entreprise (banques, gestion de bases de données, etc...)
- le développement de jeux vidéo
- etc...

Sa devise, **"Write Once, Run Anywhere" (WORA)**, veut dire qu'un programme écrit en Java peut s'exécuter sur n'importe quelle machine disposant d'une **Java Virtual Machine (JVM)**.

## Syntaxe de Java

Chaque ligne de code exécutée en Java doit se trouver dans une classe. Et le nom de la classe doit toujours commencer par une première lettre majuscule.

Par exemple, pour afficher "Bonjour, Java !" :

```java
public class Main {
  public static void main(String[] args) {
    System.out.println("Bonjour, Java !");
  }
}

```

- **`public class Main`** : on déclare une **classe** nommée `Main`. Typiquement, on utilise `Main.java` pour le nom du fichier principal et `Main` pour le nom de sa classe, celui qui sera lu par le compilateur Java.
- **`public static void main(String[] args)`** : c'est la **méthode** (appelée _fonction_ en JS ou PHP) principale, le point de départ/d'entrée du programme
- **`System.out.println("Bonjour, Java !");`** : affiche du texte dans la console

> ℹ️ Le nom du fichier **doit** correspondre au nom de la classe ! N'oubliez pas non plus d'ajouter `.java` à l'extension du fichier.

## Output (affichage dans la console)

Comme dans les autres langages (JS, PHP, etc...), Java fournit plusieurs méthodes pour afficher du texte dans la console :

- `System.out.print()` : affiche un message sans retour à la ligne
- `System.out.println()` : affiche un message suivi d'un retour à la ligne
- `System.out.printf()` : permet d'afficher du texte formaté

**Exemples** :

```java
System.out.println("Bonjour !");
System.out.print("Pas de retour à la ligne ");
System.out.print("-> et donc ce message est sur la même ligne que le message précédent !");
System.out.printf("\nIl y a %d jours en février.\n", 28);
```

↳ **Sortie** :

```
Bonjour !
Sans retour à la ligne -> et donc ce message est sur la même ligne que le message précédent !
Il y a 28 jours en février.
```

> ℹ️ Dans le cours suivant, vous découvrirez comment stocker une valeur (texte, nombre, etc...) dans [une variable](./01_variables.md).

---

## Exercices

Les exercices [00_setup](https://github.com/association-z-code-emploi/exercices-java/tree/main/00_setup) sont recommandés pour pratiquer les notions vues durant ce cours.
