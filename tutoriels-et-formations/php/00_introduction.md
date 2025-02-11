---
tags:
  - tutorials

  - php
---

# Introduction à PHP

**PHP** (_Hypertext Preprocessor_) est un langage de script principalement utilisé pour le développement web côté serveur. Il permet de générer du contenu dynamique et d'interagir avec des bases de données, notamment sur des pages webs.

## Syntaxe

Un script PHP commence toujours par `<?php` et se termine par `?>`.

```php
<?php
echo "Hello, world!";
?>
```

- chaque instruction doit se terminer par un point-virgule `;`
- on peut directement intégrer PHP dans du HTML avec `<?php ?>`
- à l'inverse, les fichiers PHP peuvent contenir du HTML

PHP ne prête pas attention à la **casse** (le fait de distinguer les lettres majuscules des minuscules, et vice-versa) pour les mots-clés et les fonctions, mais les variables sont sensibles à la casse.

## Les commentaires

Les commentaires permettent d'ajouter du texte qui sera ignoré par l'interpréteur (ce qui va exécuter le code). Souvent, les utilisations d'un commentaire sont :

- une courte description pour expliquer le code
- ajouter un mémo pour plus tard/pour une autre personne ayant accés au code
- etc...

```php
<?php
// Ceci est un commentaire sur une seule ligne

# Ceci est aussi un commentaire sur une seule ligne

/*
Ceci est un commentaire
sur plusieurs lignes.
*/
?>
```

> ⚠️ Les commentaires sont **optionnels** et **ne sont pas du code** à proprement parlé.

## Les variables

Une variable est ce qui va contenir une donnée. Pour ensuite retrouver cette donnée, on référencera son nom (comme un label ou une étiquette).

En PHP, une variable :

- a un nom qui commence par `$`
- puis par une lettre ou un `_`, mais pas par un chiffre
- ne doit pas contenir d'espaces ni de caractères spéciaux ("é", "€", "@", etc...)

```php
<?php
$nom = "Jim";
$age = 30;
?>
```

## `echo` et `print`

### `echo`

`echo` permet d'afficher du texte :

```php
<?php
echo "Hello, World!";
?>
```

### `print`

`print` fonctionne comme `echo` mais ne peut afficher qu'une seule valeur, contrairement à `echo` qui peut afficher plusieurs valeurs séparées par des virgules :

```php
<?php
print "Hello, world!";
// 👉 "Hello, world!"
?>
```

```php
<?php
echo "Nom: " . $nom . ", Âge: " . $age;
// 👉 "Nom: Jim, Âge: 30"
?>
```

---

## Exercices

Les exercices suivants sont recommandés pour ce cours-ci :

- [01_hello-world](/exercices-php/01_hello-world/README.md)
- [02_premieres-variables](/exercices-php/02_premieres-variables/README.md)
- [03_commentaires](/exercices-php/03_commentaires/README.md)
- [04_echo-vs-print](/exercices-php/04_echo-vs-print/README.md)
- [05_concatenations](/exercices-php/05_concatenations/README.md)
