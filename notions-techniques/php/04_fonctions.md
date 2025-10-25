---
tags:
  - tutorials
  - php
---

# Fonctions

Une **fonction** est un **bloc de code réutilisable** : on la définit une fois, puis on peut l'appeler autant de fois qu'on veut, sans réécrire le même code.

```php
<?php
function saluer() {
  echo "Hello, World!";
}

saluer(); // affichera "Hello, World!"
saluer(); // affichera aussi "Hello, World!"
saluer(); // etc...
?>
```

> ℹ️ Note : souvenez-vous de l'acronyme **DRY** pour **D**on't **R**epeat **Y**ourself !

---

## Paramètres

On peut **transmettre des données** à une fonction grâce à des **paramètres** :

```php
<?php
function saluer($prenom, $nom) {
  echo "Hello, $prenom $nom!";
}

saluer("John", "Rambo"); // affichera "Hello, John!"
saluer("Jane", "Austen"); // affichera "Hello, Jane!"
saluer("Toto", "Rigolo"); // etc...
?>
```

Ici, `$prenom` et `$nom` agissent comme des variables locales à la fonction : elles ne sont pas accessibles en dehors de la fonction !

> ℹ️ Note : un **paramètre** est donné à l'appel de la fonction ; qui devient un **argument** quand il est utilisé dans la fonction

---

## Renvoyer une valeur : `return`

Une fonction peut **renvoyer** une valeur au lieu de simplment afficher du texte. L'intérêt est donc de pouvoir la stocker dans une variable ou la réutiliser :

```php
function addition($a, $b) {
  return $a + $b;
}

$resultat = addition(5, 3);
echo $resultat; // affichera 8
```

⚠️ **Attention** : `return` interrompt la fonction !

> ℹ️ Note sur `echo` vs `return` :
>
> - `echo` affiche directement et ne sauvegarde rien :
>
> ```php
>  $age = 18;
>
>  echo $age + 2; // 20
>  echo $age; // 18
> ```
>
> - `return` donne une valeur que l'on peut réutiliser ailleurs

---

## Exercices

Les exercices [04_fonctions](https://github.com/association-z-code-emploi/exercices-php/tree/main/04_fonctions) sont recommandés pour pratiquer les notions vues durant ce cours.
