---
tags:
  - tutorials
  - php
---

# Les conditions

En algorithmie, les conditions permettent d'exécuter du code uniquement si certaines ... conditions (oui) sont remplies.

## `if`

`if` permet d’exécuter un bloc de code uniquement si une condition est remplie (si elle est "vraie") :

```php
if (condition) {
    // ici, le code exécuté si la condition est "vraie"
}
```

### Exemple simple

```php
<?php
$age = 18;

if ($age >= 18) {
    echo "Vous êtes majeur !";
}
?>
```

**Détails** :

- la condition `$age >= 18` est évaluée : est-ce que la valeur de `$age` est supérieure ou égale à 18 ?
- si la condition est `true`, alors le message `"Vous êtes majeur !"` est affiché
- si la condition est `false`, alors rien ne s'affiche

> ℹ️ Vous ne vous souvenez plus des opérateurs existants ? Checkez [le cours à ce sujet-ci](02_operateurs.md)

### Exemple avec plusieurs opérateurs

```php
<?php
$nombre = 10;

if ($nombre > 5 && $nombre < 20) {
    echo "Le nombre est compris entre 5 et 20.";
}
?>
```

**Détails** :

- `&&` signifie "ET" : les deux conditions doivent être vraies pour que le code s’exécute

## `if...else`

`if...else` permet d’exécuter un bloc de code si la condition est "vraie", et un autre bloc si elle est "fausse".

```php
if (condition) {
    // ici, le code exécuté si la condition est "vraie"
} else {
    // ici, le code exécuté si la condition est "fausse"
}
```

### Exemple

```php
<?php
$heure = 14;

if ($heure < 12) {
    echo "Bonjour !";
} else {
    echo "Bon après-midi !";
}
?>
```

**Détails** :

- si `$heure` est inférieur à `12`, on affiche `"Bonjour !"`
- sinon, on affiche `"Bon après-midi !"`

## Shorthand `if` (ou opérateur ternaire)

Plus simple pour certains, moins pratiques pour d'autres, PHP propose une écriture alternative pour les conditions simples, appelé l’opérateur ternaire `? :`.

```php
(condition) ? valeur_si_vrai : valeur_si_faux;
```

### Exemple

```php
<?php
$age = 20;
$message = ($age >= 18) ? "Majeur" : "Mineur";
echo $message;
?>
```

**Détails** :

- si `$age >= 18`, `$message` prend `"Majeur"`, sinon `"Mineur"`

## `if` imbriqués ("_nested if_")

Les `if` imbriqués permettent d’effectuer plusieurs conditions successivement :

### Exemple

```php
<?php
$age = 25;
$carte_etudiant = true;

if ($age < 18) {
    echo "Tarif enfant";
} else {
    if ($carte_etudiant) {
        echo "Tarif étudiant";
    } else {
        echo "Tarif adulte";
    }
}
?>
```

**Détails** :

- si `$age < 18`, on affiche `"Tarif enfant"`
- sinon, on vérifie `$carte_etudiant` pour appliquer le `"Tarif étudiant"` ou `"Tarif adulte"`

## `switch`

`switch` est une alternative aux `if...else` lorsque plusieurs conditions sont possibles :

```php
switch (variable) {
    case valeur1:
        // ici, le code exécuté si variable == valeur1
        break;
    case valeur2:
        // ici, le code exécuté si variable == valeur2
        break;
    default:
        // ici, le code exécuté si aucune condition n'est remplie
}
```

### Exemple

```php
<?php
$jour = "mardi";

switch ($jour) {
    case "lundi":
        echo "Début de semaine !";
        break;
    case "vendredi":
        echo "Presque le week-end !";
        break;
    case "samedi":
    case "dimanche":
        echo "C'est le week-end !";
        break;
    default:
        echo "Journée normale.";
}
?>
```

**Détails**

- `switch` compare `$jour` à plusieurs valeurs possibles
- `break` empêche d’exécuter les autres `case`
- si `$jour` est `"samedi"` ou `"dimanche"`, le même message est affiché

---

## Exercices

Les exercices suivants sont recommandés pour ce cours-ci :

- [18_condition-simple](https://github.com/association-z-code-emploi/exercices-php/18_condition-simple/README.md)
- [19_condition-operateurs](https://github.com/association-z-code-emploi/exercices-php/19_condition-operateurs/README.md)
- [20_if-else](https://github.com/association-z-code-emploi/exercices-php/20_if-else/README.md)
- [21_ternaire](https://github.com/association-z-code-emploi/exercices-php/21_ternaire/README.md)
- [22_if-imbriques](https://github.com/association-z-code-emploi/exercices-php/22_if-imbriques/README.md)
- [23_switch](https://github.com/association-z-code-emploi/exercices-php/23_switch/README.md)
