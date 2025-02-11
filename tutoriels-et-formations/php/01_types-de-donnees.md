---
tags:
  - ressources
  - tutorials
  - basic
  - php
---

# Les types de données ("_data types_")

PHP est un langage dit "faiblement typé" : cela signifie que vous n'avez pas besoin de spécifier explicitement le type d'une variable. Il est cependant important de connaître ce que PHP propose comme types de données : est-ce du texte ? un nombre ? une collection de variables ? etc...

## Chaînes de caractères ou _string_

Une chaîne de caractères est une suite de caractères entourée par des guillemets simples `'` ou doubles `"`.

```php
<?php
$texte1 = "Hello, World!";
$texte2 = 'Oh yeah!';

echo $texte1;
echo $texte2;
?>
```

> 📌 Différence entre guillemets simples et doubles : seules les doubles guillemets (`"`) permettent d'interpréter les variables.

## Nombres ou _number_

On distingue deux types de nombres :

- **les entiers (ou _integer_)** : nombres sans décimale
- **les nombres flottants (ou _float_ / _double_)** : nombres avec décimale (séparés par un point et non pas une virgule)

```php
<?php
$entier = 59;
$flottant = 3.14;

echo $entier;
echo $flottant;
?>
```

## Booléens ou _boolean_

Les booléens ne peuvent avoir que deux valeurs :

- `true` (vrai)
- `false` (faux)

```php
<?php
$estVrai = true;
$estFaux = false;

var_dump($estVrai); // affichera : bool(true)
var_dump($estFaux); // affichera : bool(false)
?>
```

> ℹ️ `var_dump(...)` permet de connaître le type de la donnée d'une variable

> ℹ️ Certaines valeurs sont toujours équivalentes à `false` :
>
> - `0` (zéro)
> - `""` (chaîne vide)
> - `null`
> - `[]` (tableau vide)

## Tableaux ou _array_

Les tableaux permettent de stocker plusieurs valeurs sous une seule variable.

L'**index** (la position d'un élément dans un tableau) commence à partir de 0 :

```php
<?php
$couleurs = ["rouge", "vert", "bleu"];
echo $couleurs[0]; // affichera : "rouge" car en première position, donc index 0
?>
```

Il est aussi possible d'**associer un nom à un index**, plutôt qu'automatiquement un chiffre :

```php
<?php
$personne = [
  "nom" => "Jim",
  "age" => 30
];

echo $personne["nom"]; // Affiche : Jim
?>
```

## Objets ou _object_

Un objet est un ensemble de données similaires aux arrays avec des noms associés aux indexes. La différence clée ne va pas être flagrante pour le moment, vous en apprendrez plus durant son chapitre dans un autre cours !

```php
<?php
class Personne {
  public $nom;
  public $age;

  public function __construct($nom, $age) {
    $this->nom = $nom;
    $this->age = $age;
  }

  public function saluer() {
    return "Bonjour, je suis " . $this->nom;
  }
}

$utilisateur = new Personne("Jim", 30);
echo $utilisateur->saluer(); // Affiche : Bonjour, je suis Jim
?>
```

## `null`

`null` est une variable sans valeur. Si une variable est créer sans valeur, alors elle aura par défaut une valeur `null`.

```php
<?php
$variable = null;
var_dump($variable); // affichera : NULL
?>
```

## Convertir les types ou _casting_

Comme dit au début : PHP est faiblement typé, et il permet même de convertir un type de donnée en un autre avec `(type)`.

### D'une chaîne de caractères (string) à un entier (integer) :

```php
<?php
$texte = "59";
$nombre = (int) $texte;
var_dump($nombre); // affichera : "int(59)"
?>
```

### D'une chaîne de caractères (string) à un nombre décimal (float) :

```php
<?php
$texte = "3.14";
$flottant = (float) $texte;
var_dump($flottant); // affichera : "float(3.14)"
?>
```

### D'un entier (integer) à un booléen (boolean) :

```php
<?php
$valeur = 0;
$booleen = (bool) $valeur;
var_dump($booleen); // affichera : "false"
?>
```

### D'un entier (integer) à une chaîne de caractères (string) :

```php
<?php
$nombre = 100;
$texte = (string) $nombre;
var_dump($texte); // affichera : "100"
?>
```

---

## Exercices

Les exercices suivants sont recommandés pour ce cours-ci :

- [06_strings](/exercices-php/06_strings/README.md)
- [07_numbers](/exercices-php/07_numbers/README.md)
- [08_booleans](/exercices-php/08_booleans/README.md)
- [09_arrays](/exercices-php/09_arrays/README.md)
