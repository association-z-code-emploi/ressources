---
tags:
  - tutorials
  - php
---

# Les constantes

Une **constante** est une variable dont la valeur ne peut pas être modifiée après sa définition. Contrairement aux variables, une constante :

- ne commence **pas** par `$`
- est généralement écrite en **majuscule** (par convention)
- est **globale** et accessible partout dans le fichier

## Déclarations d’une constante

On peut définir une constante en PHP avec la fonction `define()` ou le mot-clé `const`.

### `define()`

```php
<?php
define("SITE_NAME", "AssoZ");
echo SITE_NAME;
?>
```

- `define("NOM_DE_LA_CONSTANTE", valeur);`
- `SITE_NAME` est une constante contenant `"AssoZ"`
- `echo SITE_NAME;` affiche son contenu

### `const`

```php
<?php
const PI = 3.14159;
echo PI;
?>
```

> ℹ️ _Différences entre `define()` et `const`_ :
>
> | Méthode                  | Utilisation                                | Scope   |
> | ------------------------ | ------------------------------------------ | ------- |
> | `define("NOM", valeur);` | peut être utilisé dans une fonction        | Globale |
> | `const NOM = valeur;`    | ne peut pas être utilisé dans une fonction | Globale |
>
> Si vous ne savez pas encore ce qu'est une fonction, un autre cours lui est dédiée.

## Les constantes prédéfinies

PHP possède plusieurs constantes prédéfinies utiles :

| Constante     | Description             | Exemple             |
| ------------- | ----------------------- | ------------------- |
| `PHP_VERSION` | Version actuelle de PHP | `echo PHP_VERSION;` |
| `PHP_INT_MAX` | Valeur max d'un entier  | `echo PHP_INT_MAX;` |
| `PHP_OS`      | Système d’exploitation  | `echo PHP_OS;`      |

Exemple :

```php
<?php
echo "PHP Version : " . PHP_VERSION . "\n";
echo "Système : " . PHP_OS . "\n";
?>
```

## Les "Magic Constants"

Les **"magic constants"** sont des constantes spéciales définies automatiquement par PHP.
Elles commencent et finissent toujours par deux underscores (`__`), comme celles ci-dessous :

| Constante      | Description                      | Exemple              |
| -------------- | -------------------------------- | -------------------- |
| `__LINE__`     | Numéro de ligne dans le fichier  | `echo __LINE__;`     |
| `__FILE__`     | Chemin complet du fichier actuel | `echo __FILE__;`     |
| `__DIR__`      | Dossier du fichier en cours      | `echo __DIR__;`      |
| `__FUNCTION__` | Nom de la fonction actuelle      | `echo __FUNCTION__;` |
| `__CLASS__`    | Nom de la classe actuelle        | `echo __CLASS__;`    |

Et beaucoup d'autres !

**Exemple** : afficher le chemin complet du fichier

```php
<?php
echo "Ce fichier est : " . __FILE__;
?>
```

↳ `/var/www/html/index.php` (chemin complet)

---

## Exercices

Les exercices suivants sont recommandés pour ce cours-ci :

- [17](https://github.com/association-z-code-emploi/exercices-php/17_constantes/README.md)
