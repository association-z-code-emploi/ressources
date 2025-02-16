---
tags:
  - tutorials
  - php
---

# Les opérateurs

Les opérateurs permettent d'effectuer des opérations sur des variables et des valeurs.

Il en existe plusieurs catégories d'opérateurs :

1. arithmétiques
2. d’assignation
3. de comparaison
4. d'incrémentation et de décrémentation
5. logiques
6. sur les chaînes de caractères (string)
7. sur les tableaux (arrays)

## Les opérateurs arithmétiques

Ils permettent de faire des calculs mathématiques simples.

| Opérateur | Description                   | Exemple   |
| --------- | ----------------------------- | --------- |
| `+`       | addition                      | `$a + $b` |
| `-`       | soustraction                  | `$a - $b` |
| `*`       | multiplication                | `$a * $b` |
| `/`       | division                      | `$a / $b` |
| `%`       | modulo (reste de la division) | `$a % $b` |

> ℹ️ Le modulo est probablement l'opérateur que l'on utilise le moins dans la vie de tous les jours.
>
> Dans le monde de la programmation, il est utile pour savoir s'il y a reste ou non : un nombre pair n'a jamais de reste alors qu'un nombre impair si !

**Exemples :**

```php
<?php
$a = 10;
$b = 2;

echo $a + $b; // 12
echo $a - $b; // 8
echo $a * $b; // 20
echo $a / $b; // 5
echo $a % $b; // 0
?>
```

## Les opérateurs d’assignation

Ils permettent d'affecter des valeurs aux variables, avec parfois des calculs dans la foulée !

| Opérateur | Description                   | Exemple   | Équivalent à             |
| --------- | ----------------------------- | --------- | ------------------------ |
| `=`       | assignation simple            | `$a = 5`  | `$a` prend la valeur `5` |
| `+=`      | addition et assignation       | `$a += 2` | `$a = $a + 2`            |
| `-=`      | soustraction et assignation   | `$a -= 3` | `$a = $a - 3`            |
| `*=`      | multiplication et assignation | `$a *= 4` | `$a = $a * 4`            |
| `/=`      | division et assignation       | `$a /= 2` | `$a = $a / 2`            |
| `%=`      | modulo et assignation         | `$a %= 2` | `$a = $a % 2`            |

**Exemples :**

```php
<?php
$a = 10;
$a += 2; // $a vaut maintenant 12
$a *= 3; // $a vaut maintenant 36 ; car elle valait 12 juste avant cette ligne
$a /= 4; // $a vaut maintenant 9 ; car elle valait 36 juste avant cette ligne
$a %= 5; // $a vaut maintenant 4 ; car elle valait 9 juste avant cette ligne
echo $a; // au final, $a vaut 4, après toutes les réassignations précédentes
?>
```

## Les opérateurs de comparaison

Ils permettent de comparer deux valeurs et retournent `true` ("vrai") ou `false` ("faux").

| Opérateur     | Description       | Exemple     | Résultat                                              |
| ------------- | ----------------- | ----------- | ----------------------------------------------------- |
| `==`          | égal à            | `$a == $b`  | `true` si `$a` et `$b` sont égaux (valeur uniquement) |
| `===`         | identique         | `$a === $b` | `true` si `$a` et `$b` sont égaux **et** de même type |
| `!=` ou `< >` | différent         | `$a != $b`  | `true` si `$a` et `$b` sont différents                |
| `!==`         | pas identique     | `$a !== $b` | `true` si `$a` et `$b` ne sont pas identiques         |
| `>`           | supérieur à       | `$a > $b`   | `true` si `$a` est strictement supérieur à `$b`       |
| `<`           | inférieur à       | `$a < $b`   | `true` si `$a` est strictement inférieur à `$b`       |
| `>=`          | supérieur ou égal | `$a >= $b`  | `true` si `$a` est supérieur ou égal à `$b`           |
| `<=`          | inférieur ou égal | `$a <= $b`  | `true` si `$a` est inférieur ou égal à `$b`           |

> 💭 Pourquoi faire la différence entre `==` ("égal à") et `===` ("identique") ?
>
> `==` tente de comparer plusieurs valeurs, même d'un type différent
>
> `===` comparer plusieurs valeurs avec leurs types, qui doivent être identiques

**Exemple :**

```php
<?php
$a = 12;
$b = "12";

var_dump($a == $b);  // renvoie true (car les valeurs similaires)
var_dump($a === $b); // renvoie false (car les types différents)
var_dump($a != $b);  // renvoie false (car les valeurs similaire)
var_dump($a !== $b); // renvoie true (car les types différents)
?>
```

## Les opérateurs d'incrémentation et de décrémentation

Similaires aux opérateurs d'assignations, ils permettent de directement mettre à jour les valeurs aux variables, avant ou après après utilisation/réassignation.

| Opérateur | Description                                         | Exemple                                                     |
| --------- | --------------------------------------------------- | ----------------------------------------------------------- |
| `++$a`    | Pré-incrémentation (ajoute de 1 avant utilisation)  | `++$a` soit `$a` augmente de 1                              |
| `$a++`    | Post-incrémentation (utilise puis ajoute de 1)      | `$b = $a++` soit `$b` sera `$a` avant d'augmenter `$a` de 1 |
| `--$a`    | Pré-décrémentation (diminue de 1 avant utilisation) | `--$a` soit `$a` diminue de 1                               |
| `$a--`    | Post-décrémentation (utilise puis diminue de 1)     | `$b = $a--` soit `$b` sera `$a` avant de diminuer `$a` de 1 |

**Exemple :**

```php
<?php
$a = 12;
$b = null;

++$a; // $a vaut 13, à partir de maintenant
$b = $a++; // $b vaut 13 (car $a valait 13 juste avant cette ligne), et $a vaut maintenant 14

$c = 42;
$d = null;

$c--; // $a vaut 41, à partir de maintenant
$d = $c--; // $d vaut 41 (car $c valait 41 juste avant cette ligne), et $c vaut maintenant 40
?>
```

## Les opérateurs logiques

Ils permettent de combiner plusieurs conditions pour entre deux éléments.

| Opérateur      | Description                                 | Exemple                 |
| -------------- | ------------------------------------------- | ----------------------- |
| `&&` ou `and`  | ET (les deux)                               | `($a > 0 && $b < 10)`   |
| `\|\|` ou `or` | OU (l'un ou l'autre, ou les deux)           | `($a > 0 \|\| $b < 10)` |
| `!`            | NON ("n'est pas")                           | `!($a > 0)`             |
| `xor`          | OU exclusif (l'un ou l'autre, pas les deux) | `($a > 0 xor $b < 10)`  |

**Exemple :**

```php
<?php
$a = 5;
$b = 10;

var_dump($a > 0 && $b < 20); // renverra true car $a est bien supérieur à 0 et $b est bien inférieur à 20
var_dump($a > 0 || $b < 20); // renverra true car $a est bien supérieur à 0 ou $b est bien inférieur à 20, l'un ou l'autre
var_dump(!($a > 0)); // renverra false car on vérifiait ici si $a n'était pas supérieur à 0, alors qu'il est supérieur à 0
var_dump(!($a < 0)); // renverra true car on vérifiait ici si $a n'était pas inférieur à 0, alors qu'il est supérieur à 0
?>
```

> ℹ️ Si vous avez des difficultés à comprendre les conditions, un cours dédié au sujet sera bientôt ajouté à ce repo !

## Les opérateurs sur les chaînes de caractères (string)

Ils permettent de joindre des strings ensemble, pendant une initialisation ou un réassignation. On parle aussi de concaténations.

| Opérateur | Description                  | Exemple                        |
| --------- | ---------------------------- | ------------------------------ |
| `.`       | concaténation                | `$texte = "Hello " . "World";` |
| `.=`      | concaténation et assignation | `$texte .= "PHP";`             |

**Exemple :**

```php
<?php
$prenom = "Jim";
$nom = "Othis";
$nomComplet = $prenom . " " . $nom;

echo $nomComplet; // Jim Othis
?>
```

## Les opérateurs sur les tableaux (arrays)

| Opérateur | Description                                                                | Exemple         |
| --------- | -------------------------------------------------------------------------- | --------------- |
| `+`       | fusionne plusieurs tableaux à la suite                                     | `$c = $a + $b;` |
| `==`      | vérifie si les tableaux ont les mêmes clés/valeurs, peu importe l'ordre    | `$a == $b`      |
| `===`     | comme `==` mais vérifie aussi l’ordre des éléments                         | `$a === $b`     |
| `!=`      | vérifie si les tableaux sont similaires sans regarder l'ordre des éléments | `$a != $b`      |
| `!==`     | comme `!=` mais vérifie aussi que l’ordre des éléments n'est pas identique | `$a !== $b`     |

**Exemple :**

```php
<?php
$a = ["nom" => "Jim"];
$b = ["age" => 30];

$c = $a + $b;
print_r($c); // Array ( [nom] => Jim [age] => 30 )

$d = array("1" => "Banane", "2" => "Pomme");
$e = array("2" => "Pomme", "1" => "Banane");
var_dump($d != $e); // renverra false, car sans regarder l'ordre, l'array est différent
var_dump($d !== $e); // renverra true, car l'ordre est au moins différent
?>
```

---

## Exercices

Les exercices suivants sont recommandés pour ce cours-ci :

- [10_arithmetiques](https://github.com/association-z-code-emploi/exercices-php/10_arithmetiques/README.md)
- [11_assignations](https://github.com/association-z-code-emploi/exercices-php/11_assignations/README.md)
- [12_comparaisons](https://github.com/association-z-code-emploi/exercices-php/12_comparaisons/README.md)
- [13_incrementations-decrementations](https://github.com/association-z-code-emploi/exercices-php/13_incrementations-decrementations/README.md)
- [14_operations-logiques](https://github.com/association-z-code-emploi/exercices-php/14_operations-logiques/README.md)
- [15_fusion-arrays](https://github.com/association-z-code-emploi/exercices-php/15_fusion-arrays/README.md)
- [16_combinaison-operateurs](https://github.com/association-z-code-emploi/exercices-php/16_combinaison-operateurs/README.md)
