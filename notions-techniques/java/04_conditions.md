---
tags:
  - tutorials
  - java
---

# Les conditions

Jusqu'à maintenant, on a pu voir :

- les variables
- les types de données (primitives et non-primitives/référencées)
- des opérateurs, pour calculer, assigner, comparer, etc...

En parlant de comparaison, les **conditions** vont permettre de pousser un peu plus le concept de comparaison et de validation.

## Contrôler le _flow_

Un autre mot important pour indiquer que l'on souhaite choisir une partie du code à exécuter sous certaines conditions. Le _flux_ de contrôle (_flow_ en anglais) de base est "si telle condition est vraie, alors fait quelque chose, sinon fait autre chose", et c'est là que les booléens, les opérateurs de comparaison et ceux de logiques vont devenir utiles !

### Syntaxe de base

```java
if (condition1) { // Si condition1 est vraie, alors ...
    ...
} else if (condition2) { // Sinon, si condition2 est vraie, alors ...
    ...
} else { // Sinon, si aucune condition n'est vraie, alors ...
    ...
}
```

**Exemple** :

```java
public class CheckAge {
    public static void main(String[] args) {
        int age = 9;

        if (age >= 18) {
            System.out.println("Vous êtes majeur!");
        } else if (age = 17) {
            System.out.println("Presque majeur ... mais toujours mineur!");
        } else {
            System.out.println("Vous êtes mineur.");
        }
    }
}
```

## Opérateur ternaire

La version raccourcie de **`if...else`** permet d'écrire une condition plus compacte :

```java
variable = (condition) ? valeur_si_vrai : valeur_si_faux;
//              ↑      ↑        ↑       ↑        ↑
//              1      2        3       4        5
```

1. La condition (ce qu'on veut vérifier)
2. Un point d'interrogation (ce qui va déclencer la condition)
3. Le code "réponse" déclenchée si la condition est `true`
4. Les deux points qui sépareront les deux réponses
5. Le code "réponse" déclenchée si la condition est `false`

**Exemple :**

```java
public class CheckAge {
    public static void main(String[] args) {
        int age = 12;
        String message = (age >= 18) ? "Majeur" : "Mineur";

        System.out.println(message);
    }
}
```

- si `age >= 18`, la variable `message` vaut `"Majeur"`, sinon `"Mineur"`
- cela évite d'écrire un `if...else` plus long, mais avec un risque d'être moins lisible par les codeurs par la suite

---

## Exercices

Les exercices [04_conditions](https://github.com/association-z-code-emploi/exercices-java/tree/main/04_conditions) sont recommandés pour pratiquer les notions vues durant ce cours.
