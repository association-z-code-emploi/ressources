---
tags:
  - tutorials
  - java
---

# Les boucles

Elles permettent d'exécuter plusieurs fois un même bloc de code.

## `while` (tant que ...)

Une boucle `while` répète l'exécution **tant que** la condition est vraie :

```java
while (condition) {
    // ici le code est exécuté seulement si la condition est vraie
}
```

**Exemple** : pour afficher des nombres de 1 à 5

```java
public class AfficherNombres {
    public static void main(String[] args) {
        int i = 1;
        //  ↑
        //  1

        while (i < 5) {
              //  ↑
              //  2
            System.out.println("i = " + i);
            i++;
        //   ↑
        //   3
        }
    }
}
```

1. il est habituel d'utiliser `i`, `j`, `k`, etc... pour définir un "compteur de boucle" ; peu importe vraiment le nom, tant qu'il n'est pas utilisé autre part
2. la condition qui, tant qu'elle est vraie, va permettre à l'instruction de la boucle de s'exécuter
3. on augmente (ou "incrémente") la valeur de `i` de +1

> ⚠️ Il est important d'avoir **une sortie de boucle** : sans incrémenter `i`, la condition (`i < 5`) serait toujours vraie et s'exécutera sans jamais s'arrêter ... ou presque car un ordinateur récent sait maintenant reconnaître _une boucle infinie_ et couper le programme.
> Autrement, il est possible de faire Ctrl+C pour l'arrêter manuellement (boucle infinie ou non).

Si on exécute le code ci-dessus, on affichera :

```shell
1
2
3
4
```

## `do...while`

Une boucle `do...while` fonctionne comme `while`, **mais elle s'exécute au moins une fois**, même si la condition est false :

```java
do {
    // ici le code est exécuté au moins une fois, même si la condition est fausse
} while (condition);
```

**Exemple** : toujours pour afficher des nombres de 1 à 5

```java
public class AfficherNombres {
    public static void main(String[] args) {
        int i = 1;

        do {
            System.out.println("i = " + i);
            i++;
        } while (i < 5);
    }
}
```

Si on exécute le code ci-dessus, le résultat sera le même que précédemment :

```shell
1
2
3
4
```

## `for`

Une boucle `for` est souvent utilisée quand **on connaît ou que l'on peut connaître le nombre de répétitions** à faire :

```java
for (initialisation; condition; incrémentation) {
    // ici, le code exécuté tant que la condition est vraie
}
```

**Exemple** : encore une fois, pour afficher des nombres de 1 à 5

```java
public class AfficherNombres {
    public static void main(String[] args) {
        for (int i = 1; i < 5; i++) {
            //     ↑      ↑     ↑
            //     1      2     3
            System.out.println("i = " + i);
        }
    }
}
```

1. avec `for`, il est possible d'initialiser une variable temporaire (ici `i`) pour définir le compteur de boucle
2. la condition, comme avec les autres types de boucles
3. cette fois-ci, on doit définir ce qui se passera en fin de boucle ; ici augmenter `i` de +1

## Boucles imbriquées (`nested loops`)

Une boucle peut être **imbriquée** dans une autre :

**Exemple** : pour afficher les compteurs de chaque boucle

```java
public class DisplayLoops {
    public static void main(String[] args) {
        for (int i = 1; i < 5; i++) {
            for (int j = 1; j <= 5; j++) {
                System.out.println("i: "+ i + " j: " + j);
            }
        }
    }
}
```

Si on exécute le code ci-dessus :

```shell
i: 1 j: 1
i: 1 j: 2
i: 1 j: 3
i: 1 j: 4
i: 2 j: 1
i: 2 j: 2
i: 2 j: 3
i: 2 j: 4
i: 3 j: 1
i: 3 j: 2
i: 3 j: 3
i: 3 j: 4
i: 4 j: 1
i: 4 j: 2
i: 4 j: 3
i: 4 j: 4
i: 5 j: 1
i: 5 j: 2
i: 5 j: 3
i: 5 j: 4
```

## `break` et `continue`

### `break`

`break` **interrompt** une boucle immédiatement :

```java
for (int i = 1; i < 5; i++) {
    if (i == 2) {
        break; // arrête la boucle à i = 2
    }
    System.out.println(i);
}
```

```shell
1
2
```

### `continue`

`continue` **saute l’itération en cours**, et passe directement à la suivante :

```java
for (int i = 1; i < 5; i++) {
    if (i == 3) {
        continue; // ignore i = 3
    }
    System.out.println(i);
}
```

```shell
1
2
4
```

---

## Exercices

Les exercices [05_boucles](https://github.com/association-z-code-emploi/exercices-java/tree/main/05_boucles) sont recommandés pour pratiquer les notions vues durant ce cours.
