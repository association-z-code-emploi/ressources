---
tags:
  - tutorials
  - php
---

# Variables

Les variables sont des espaces nommés qui servent à stocker des valeurs pour pouvoir les réutiliser ou les modifier :

```php
<?php
  $prenom = "Zoey";
  $age = 18;

  echo $prenom;
?>
```

> ℹ️ Règles de nommage :
>
> - commence par `$`
> - doit commencer par une lettre ou un `\_`
> - ne contient pas d’espace ni de caractères spéciaux
> - respecte la casse ($nom ≠ $Nom)

### Les types de données

#### Chaînes de caractères

On parle de **chaînes de caractères** (ou _string_) pour du **texte**, indiqué entre **guillemets** :

```php
$prenom = "euh";
$region = "Hauts-de-France";
$codePostal = "59000";

$prenom = "John";
```

> ℹ️ Note :
>
> - de simples guillemets suffisent, mais des doubles est un meilleur réflexe à avoir - on y reviendra plus tard
> - réutiliser une variable en lui donnant nouvelle une valeur la réaffecte, devenant la nouvelle valeur

#### Nombres

PHP distingue les valeurs numériques en deux catégories :

- les **nombres entiers** (ou _integer_)
- les **nombres à virgules** (ou _float_)

Aucune **guillemets** pour des nombres :

```php
$achat1 = 18;
$achat2 = 12.5;
$achat3 = 8.5;
$total = $achat1 + $achat2 + $achat3;

echo $total; // affichera 39
```

##### Vite fait : addition vs concaténation

On aura une erreur si on additionne des strings. On parle alors d'addition pour des nombres et d'une concaténation pour des strings :

```php
$achat1 = 18;
$achat2 = 12.5;

echo $achat1 + $achat2;

$prenom = "Zoey";
$nom = "Coda";
echo $prenom . $nom;
```

> ℹ️ Note : vos résultats sont cote à cote ?
>
> - ajoutez des espaces comme strings pour rester sur une même ligne
> - pour faire un retour à la ligne :
>   - soit en ouvrant/fermant des blocs PHP
>   - soit en utilisant des caractères spéciaux (dans la [doc](https://www.php.net/manual/fr/language.types.string.php) : Variables > Chaînes) comme `\n`

#### Booléen

Un **booléen** (ou _boolean_) est une valeur **logique** et **binaire** avec "vrai" ou "faux" :

```php
$faim = true;
$soif = false;
```

> ℹ️ Note : c'est le principe fondamental derrière n'importe quelle condition ; on y reviendra plus tard

---

#### `null`

Une variable contenant une valeur `null` indique **qu'il n'y a pas de valeurs**.

```php
$prenom = null;
$nom;

echo $prenom; // n'affichera rien
```

> ℹ️ Note : il sera parfois utile d'explicitement indiquer "qu'il n'y a rien dans cette variable mais qu'elle existe bel et bien"

#### Tableaux

Un **tableau** (ou _array_) est un **ensemble de valeurs**, regroupées **entre crochets** dans une seule variable :

```php
$nourritures = ["pomme",  "poire",  "banane"];
//                ⬆         ⬆         ⬆
//index:          0          1          2

echo $nourritures[0]; // "pomme"
echo $nourritures[2]; // "banane"
```

Pour accéder à un élément de ce tableau, on devra indiquer son **index** - qui commence toujours par 0.

> ℹ️ Note :
>
> - le type de données des éléments peuvent être différents les uns des autres ... dont de nouveaux tableaux !
> - dans d'anciennes versions de PHP, [les tableaux s'écrivaient différemment](https://www.php.net/manual/fr/language.types.array.php) (encore valable) avec `$notes = array(...)`

#### Récap' des types de données

| Type                  | Description                |
| --------------------- | -------------------------- |
| **String (chaîne)**   | Texte                      |
| **Integer (entier)**  | Nombre sans décimales      |
| **Float (réel)**      | Nombre à virgule           |
| **Boolean (booléen)** | Valeur logique (vrai/faux) |
| **NULL**              | Variable sans valeur       |
| **Array (tableau)**   | Ensemble de valeurs        |

---

> ℹ️ Dans le cours suivant, vous découvrirez les [conditions](./02_conditions.md) pour exécuter certaines instructions selon certaines ... condtions !

---

## Exercices

Les exercices [01_variables](https://github.com/association-z-code-emploi/exercices-php/tree/main/01_variables) sont recommandés pour pratiquer les notions vues durant ce cours.
