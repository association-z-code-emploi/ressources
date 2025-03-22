---
tags:
  - tutorials
  - java
---

# Les méthodes

Au cours des jours précédents, vous avez pu créer vos premiers programmes, et joué avec :

- des **variables**
- des **types de données**, pour les valeurs de ces variables
- des **opérateurs** pour manipuler ces valeurs
- des **conditions**
- des **boucles**

Et si on veut écrire un programme qui calcule une donnée qu'on ne connait pas d'avance ?
Par exemple, calculer le prix d'un appartement selon sa surface et sa localisation ? Ou ajuster une recette selon le nombre de personnes reçu ?

Vous verrez qu'on devra exécuter les mêmes instructions plusieurs fois de suite.

Que se passerait-il si on doit effectuer un même calcul à plusieurs endroits d'un programme ? On pourrait copiez et collez simplement le même code, mais on enfreindrait l'un des principes les plus importants de la programmation :

> 📝 **DRY** (_Don't Repeat Yourself_ ; "Ne pas se répéter")

## Des séquences aux méthodes

Précédemment, on a assemblé des morceaux de code pour "faire des choses". Les **méthodes** permettent de regrouper ces morceaux pour les réutiliser. Concrètement, c'est un moyen de regrouper une série d'instructions auxquelles on peut attribuer des paramètres d'entrée.

Les **méthodes** sont similaires aux fonctions mathématiques (même principe avec le nom de "fonction" dans d'autres langages que Java), et il existe de nombreuses analogies dans la vie réelle. Prenons l'exemple d'une vente (comme à Décathlon) :

`ProduitDemande -> PaiementCaisse -> ProduitVendu`

Dans cet exemple :

- `ProduitDemande` est une entrée (ou un argument, ou un paramètre)
- `PaiementCaisse` est une méthode
- `ProduitVendu` est le résultat de l'application

Dans l'exemple précédent, la méthode pourrait prendre la forme suivante : `acheter (quoi, quantité)`.

> ℹ️ Une méthode doit avoir la responsabilité COMPLÈTE d’UNE tâche.
>
> C'est le principe de responsabilité unique, ou "**S**ingle **R**esponsibility **P**rinciple".
>
> Cela permet d’avoir un meilleur contrôle sur toutes les méthodes et d’appliquer la règle _Diviser pour mieux régner_.

Une introduction plus longue que d'habitude, mais les méthodes sont élements si importants qu'ils le méritaient bien ! Maintenant, pour écrire une méthode ...

## Définition et appel d'une méthode

### Définition

Une méthode doit être définie/écrite/déclarée/initialisée (synonymes) dans une classe.

```java
public class Main {
  static void maMethode() {
    ...
  }
}
```

- `static` signifie que la méthode appartient à la classe Main, et non à un objet de cette classe. On en apprendra plus sur les objets et sur l'accès aux méthodes dans un prochain cours
- `void` signfie que cette méthode n'a pas de valeur de retour ("_return_"). On en apprendra plus sur les valeurs de retour un peu plus bas
- `maMethode()` est le nom de la méthode
- `{ ... }` contient l'instruction à exécuter quand la méthode est appelée ("_called_")

Java fournit aussi certaines méthodes prédéfinies, telles que `System.out.println()` qu'on connait maintenant bien. Le plus intéressant reste de créer ses propres méthodes pour des besoins qui ne sont pas pré-existants dans Java.

### Appel

Pour appeler/invoquer une méthode, il suffit de donner son nom, suivi par deux parenthèses `()` et un point virgule `;`.

```java
public class Main {
  static void maMethode() {
    System.out.println("Coucou!");
  }

  public static void main(String[] args) {
    maMethode();
  }
}

// Output (dans le terminal) : "Coucou!"
```

> ℹ️ L'intérêt d'une méthode est donc de pouvoir la réutiliser : on pourrait appeler de nouveau la méthode `maMethod()`, autant de fois qu'on le voudra !

## Les paramètres

### Paramètres et arguments

Une méthode peut avoir un ou plusieurs paramètres, qui seront fournis par le code qui appele la méthode et qui pourront être utilisés à l'intérieur de cette méthode.

Ces paramètres sont des variables, qui sont comme un "emplacement réservé" et qui sera remplacé par les données que l'on fournira lors de l'appel de la méthode.

```java
public class Main {
  static void direQuelqueChose(String mot) {
    System.out.println(mot);
  }

  public static void main(String[] args) {
    direQuelqueChose("Hello");
    direQuelqueChose("Plop");
    direQuelqueChose("euh");
  }
}

// Output : "Hello"
// Output : "Plop"
// Output : "euh"
```

↳ `String mot` :

- `String` est le type du paramètre qui se reçu
- `mot` est le nom du paramètre, qui prendra la valeur donnée pendant l'appel (par exemple "Hello") et ce paramètre n'est utilisable que durant l'exécution de la méthode

> ℹ️ Quand un **paramètre** est transmis à une méthode, il est alors appelé un **argument**. Donc dans l'exemple précédent `mot` est un paramètre, alors que `"Hello"`, `"Plop"` et `"euh"` sont des arguments.

### Attendre plusieurs paramètres

Il est possible pour une méthode d'attendre autant de paramètre qu'on le désire :

```java
public class Main {
  static void sePresenter(String prenom, String nom, Int age) {
    System.out.println("Bonjour, je suis " + prenom + " " + nom + " et j'ai " + age + " ans.");
  }

  public static void main(String[] args) {
    sePresenter("Jim", "Feddy", 32);
  }
}

// Output : "Bonjour, je suis Jim Feddy et j'ai 32 ans."
```

> ℹ️⚠️ La méthode doit recevoir autant d'arguments qu'elle en attend, et doit les recevoir dans le même nombre et le même ordre que les paramètres :
>
> - avec `sePresenter("Feddy", 32, "Jim")` on aurait "Feddy" pour "`prenom`", et "32" pour `nom` qui n'est en plus pas du bon type !
> - avec `sePresenter("Jim", "Feddy")`, il y a un argument manquant, ou avec `sePresenter("Jim", "Feddy", 32, "j'aime bien java")`, il y a un argument de trop

## Valeur de retour ("_return_")

Jusqu'à présent, on a indiqué `void` comme valeur de retour car tout ce que l'on a fait, c'est afficher quelque chose dans le terminal. C'est un message, on n'en fera rien de plus que le lire une fois. Si on veut que la méthode renvoie une valeur (ie. un résultat) que l'on pourra réutiliser, on peut utiliser un autre type (comme `int`, `boolean`, etc...) :

```java
public class Main {
  static String direBonjour(String prenom) {
    return "Bonjour " + prenom;
  }

  public static void main(String[] args) {
    String salutation1 = direBonjour("Jim");
    System.out.println(salutation1)

    String salutation2 = direBonjour("Zack");
    System.out.println(salutation2)
  }
}

// Output : "Bonjour Jim"
// Output : "Bonjour Zack"
```

- `static String direBonjour` : on a changé `void` en `String` car c'est le type de donné que l'on va retourner
- `return ...` : c'est ici que l'on va donner la valeur à retourner, qui sera ensuite stockée dans une variable, et qui sera elle-même affichée avec `System.out.println()`

## Portée ("_scope_")

En Java, les variables sont uniquement accessibles/utilisables qu'après avoir été déclarée, pas avant !

```java
public class Main {
  static String direBonjour(String prenom) {
    return "Bonjour " + prenom;
  }

  public static void main(String[] args) {
    System.out.println(salutation)
    String salutation = direBonjour("Jim");
  }
}
```

↳ **Erreur** : `salutation` est appelée avant d'être initialisée !

Aussi, comme indiqué précédement, les paramètres sont des variables qui n'existent que durant l'appel et l'exécution d'une méthode. Cela signifie aussi qu'on ne peut pas appeler directement les paramètres en dehors de l'exécution de la méthode :

```java
public class Main {
  static String direBonjour(String prenom) {
    return "Bonjour " + prenom;
  }

  public static void main(String[] args) {
    System.out.println(prenom)
  }
}
```

↳ **Erreur** : `prenom` n'existe que dans la méthode `direBonjour()` !

> ℹ️ Un comportement similaire existe durant un `if...else` ou une boucle : si on initialise une variable _pendant_ l'un de ces "**blocs de code**", la variable n'existe que pendant que l'exécution s'y trouve.

---

## Bonus : les récursions

Il est possible que durant l'exécution de l'instruction d'une méthode, celle-ci s'appelle elle-même, comme un genre de boucle :

```java
public class Main {
  static void incrementation(int compteur) {
    if(compteur < 10) {
      System.out.println(compteur);
      incrementation(compteur + 1);
    }
  }

  public static void main(String[] args) {
    incrementation(0);
  }
}

// Output :
// 0
// 1
// 2
// ...
// 7
// 8
// 9
```

↳ Quand la méthode `incrementation()` est appelée, elle vérifie si le nombre fourni est inférieur à 10 ou non. Si c'est le cas, elle s'appelle elle-même en augmentant le nombre de 1, puis elle recommence : elle vérifie, si inférieur à 10, elle s'appelle une nouvelle fois en augmentant le nombre de 1, etc...

> ⚠️ Comme avec n'importe quelle boucle, il faut une condition d'arrêt pour que la fonction cesse de s'appeler. Prenez garde aux boucles infinies !

---

## Exercices

Les exercices [06_methodes](https://github.com/association-z-code-emploi/exercices-java/tree/main/06_methodes) sont recommandés pour pratiquer les notions vues durant ce cours.
