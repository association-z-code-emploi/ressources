---
tags:
  - tutorials
  - javascript
---

# Variables

Les variables permettent de **stocker des valeurs** qu’on peut **réutiliser ou modifier** :

```js
let prenom = "Zoey";
let age = 18;

console.log(prenom);
```

> ℹ️ **Règles de nommage :**
>
> - ne commence **pas** par un chiffre
> - **aucun espace** ni caractères spéciaux
> - sensible à la casse (`prenom` ≠ `Prenom`)
> - éviter les mots réservés (comme `let`, `if`, etc.)

---

## Trois mots-clés possibles :

| Mot-clé | Signification                         |
| ------- | ------------------------------------- |
| `var`   | ancienne façon (à éviter aujourd’hui) |
| `let`   | variable **modifiable**               |
| `const` | variable **non modifiable**           |

---

## Types de données

### Chaînes de caractères

Des **chaînes** (ou _strings_) servent à stocker du **texte**, entre guillemets simples ou doubles :

```js
let animal = "chat";
let race = "siamois";
let phrase = "Mon " + animal + " est " + race + ".";

console.log(phrase);
```

> ℹ️ Entre _backticks_ (\` \`), on peut écrire plus simplement :
>
> ```js
> console.log(`Mon ${animal} est ${race}.`);
> ```

### Nombres

Les **nombres** peuvent être entiers ou à virgule :

```js
let prix1 = 12;
let prix2 = 3.5;
let total = prix1 + prix2;

console.log(total); // 15.5
```

#### Addition vs Concaténation

En JS, `+` peut **additionner** ou directement **concaténer** :

```js
let a = 5;
let b = "10";

console.log(a + b); // "510" (texte)
console.log(a + Number(b)); // 15 (nombre)
```

### Booléens

Un **booléen** (_boolean_) peut valoir `true` (vrai) ou `false` (faux) :

```js
let faim = true;
let soif = false;
```

### `null` et `undefined`

- `null` : il n’y a **aucune valeur**
- `undefined` : la variable **n’a pas encore été définie**

```js
let prenom = null;
let nom;

console.log(prenom); // null
console.log(nom); // undefined
```

### Tableaux

Un **tableau** (ou _array_) regroupe plusieurs valeurs dans une seule variable :

```js
let fruits = ["pomme", "poire", "banane"];

console.log(fruits[0]); // "pomme"
console.log(fruits[2]); // "banane"
```

Pour accéder à un élément de ce tableau, on devra indiquer son **index** - qui commence toujours par 0.

### Récapitulatif des types

| Type          | Exemple          |
| ------------- | ---------------- |
| **String**    | `"Salut"`        |
| **Number**    | `42` ou `3.14`   |
| **Boolean**   | `true` / `false` |
| **Null**      | `null`           |
| **Undefined** | `undefined`      |
| **Array**     | `[1, 2, 3]`      |

---

> ℹ️ Dans le cours suivant, vous découvrirez les [conditions](./02_conditions.md) pour exécuter certaines instructions selon certaines ... condtions !

---

## Exercices

Les exercices [01_variables](https://github.com/association-z-code-emploi/exercices-javascript/tree/main/01_variables) sont recommandés pour pratiquer les notions vues durant ce cours.
