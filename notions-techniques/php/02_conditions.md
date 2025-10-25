---
tags:
  - tutorials
  - php
---

# Conditions

---

## Introduction

Les conditions permettent d’exécuter du code uniquement si un test est **vrai** :

```php
<?php
$temperature = 17;

if ($temperature > 30) { // ⬅ 1
  echo "Il fait chaud";
} else { // ⬅ 2
  echo "Il fait frais";
}
?>
```

1. `if` est la condition à vérifier et doit être "vraie" pour exécuter son code
2. `else` est le code à exécuter si la condition n'est pas "vraie"

> ℹ️ Note : l'exécution de la condition (partie entre parenthèses ici) renvoie un booléen : s'il est `true`, alors la condition est valide

On peut ajouter `elseif` pour vérifier d'autres conditions après un `if` qui ne serait pas vrai :

```php
<?php
$temperature = 17;

if ($temperature > 30) { // ⬅ 1
  echo "Il fait chaud";
} elseif ($temperature > 20) { // ⬅ 2
  echo "Il fait bon";
} else { // ⬅ 3
  echo "Il fait frais";
}
?>
```

1. `if` vérifie si la première condition est vraie
2. `elseif` vérifie sinon une autre condition
3. `else` est le cas "de secours" si aucune condition avant n'est vraie

> ℹ️ Note : l'ordre à donc une importance dans l'exécution du code puisqu'une condition "vraie" (`true`) stoppe l'ensemble de la condition est ne fera aucune autre vérification

---

## Comparateurs et opérateurs logiques

Pour écrire des conditions, on utilise des **comparateurs** :

| Comparateur | Signification      |
| ----------- | ------------------ |
| `==`        | égal à             |
| `===`       | strictement égal à |
| `!=`        | différent de       |
| `>`         | supérieur à        |
| `<`         | inférieur à        |
| `>=`        | supérieur ou égal  |
| `<=`        | inférieur ou égal  |

> ℹ️ Note : ne pas confondre `=` et `==` :
>
> - `=` assigne ou réaffecte une valeur à une variable
> - `==` compare deux valeurs (flexible sur le typage)
> - `==` compare deux valeurs (intransigeant sur le typage)

Et des **opérateurs logiques** pour combiner des conditions :

| Opérateur | Signification |
| --------- | ------------- |
| `&&`      | "et" logique  |
| `\|\|`    | "ou" logique  |
| `!`       | "non" logique |

---

> ℹ️ Dans le cours suivant, vous découvrirez les [boucles](./03_boucles.md) pour répéter une exécution !

---

## Exercices

Les exercices [02_conditions](https://github.com/association-z-code-emploi/exercices-php/tree/main/02_conditions) sont recommandés pour pratiquer les notions vues durant ce cours.
