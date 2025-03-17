---
tags:
  - tutorials
  - java
---

# Les opérateurs

Permettent d’effectuer des calculs, des comparaisons et des opérations logiques. Ils sont utilisés pour manipuler des variables et des valeurs.

## Opérateurs arithmétiques

Permettent d’effectuer des opérations mathématiques sur des nombres (`int`, `double`, ...) :

```java
public class OperateursArithmetiques {
    public static void main(String[] args) {
        int a = 10, b = 3;

        System.out.println("Addition : " + (a + b));  // 13
        System.out.println("Soustraction : " + (a - b));  // 7
        System.out.println("Multiplication : " + (a * b));  // 30
        System.out.println("Division : " + (a / b));  // 3 (division entière)
        System.out.println("Modulo : " + (a % b));  // 1 (le reste d'une division)
    }
}
```

> ℹ️ Pour la division entière (`int / int`), **le résultat est un entier** !
>
> Pour obtenir un **résultat avec une valeur décimale**, utilisez des valeurs `double` :
>
> ```java
> double x = 10, y = 3;
> System.out.println((x / y)); // 3.3333
> ```

## Opérateurs d’assignement

Permettent d’attribuer une valeur à une variable :

```java
public class OperateursAssignement {
    public static void main(String[] args) {
        int a = 10;

        a += 5;  // a = a + 5
        System.out.println(a);  // 15

        a *= 2;  // a = a * 2
        System.out.println(a);  // 30

        a /= 3;  // a = a / 3
        System.out.println(a);  // 10
    }
}
```

> ℹ️ **À quoi servent ces assignements ?**
>
> - Ça évite de répéter le nom de la variable
> - Ça améliore la lisibilité du code

## Opérateurs de comparaison

Sont utilisés pour **comparer deux valeurs** et renvoient toujours un **résultat `true` ou `false`** (`boolean`) si la comparaison est respectivement **vraie** ou **fausse** :

```java
public class OperateursComparaison {
    public static void main(String[] args) {
        int a = 10, b = 3;

        System.out.println((a == b));  // false
        System.out.println((a != b));  // true
        System.out.println((a > b));  // true
        System.out.println((a < b));  // false
    }
}
```

> ℹ️ **Quelle est la différence entre `=` et `==` ?**
>
> - `a = b` signifie que `a` prend la valeur de `b` ; on affecte une variable avec une nouvelle valeur
> - `a == b` teste si `a` est égal à `b` ; on compare deux valeurs

## Opérateurs logiques

Permettent de **combiner plusieurs conditions** et renvoient toujours un **résultat `true` ou `false`** (`boolean`) si le résultat du test est respectivement **vrai** ou **faux** :

> ⚠️ Une partie du code ci-dessous (`if...else`) sera expliqué dans le prochain cours : "Conditions"

```java
public class OperateursLogiques {
    public static void main(String[] args) {
        int age = 25;
        boolean estMajeur = age >= 18; // Est-ce que 25 (age) est plus grand ou égal à 18 ? → oui, donc "true" !
        boolean aPermis = true;

        if (estMajeur && aPermis) { // "si estMajeur ET aPermis sont tous deux vrais ..."
            System.out.println("Vous avez le droit de conduire.");
        }

        if (estMajeur || aPermis) { // "si estMajeur OU aPermis est faux ..."
            System.out.println("Vous avez au moins une des deux conditions pour avoir le droit de conduire.");
        }

        if (!estMajeur) { // "si estMajeur est faux ..."
            System.out.println("Vous êtes mineur : vous ne pouvez pas encore passer l'examen pour conduire seul !");
        }
    }
}
```

---

## Exercices

Les exercices suivants sont recommandés pour ce cours-ci :

- [TBA](#) 🚧
