---
tags:
  - tutorials
  - javascript
---

# Fonctions

Une **fonction** est un bloc de code réutilisable :

```js
function saluer() {
  console.log("Hello, world !");
}

saluer();
saluer();
```

---

## Paramètres

```js
function saluer(prenom, nom) {
  console.log(`Hello, ${prenom} ${nom} !`);
}

saluer("John", "Rambo");
saluer("Jane", "Austen");
```

> ⚠️ Les paramètres sont **locaux** à la fonction : ils ne sont pas accessibles en dehors.

---

## Retourner une valeur : `return`

Une fonction peut **renvoyer une valeur** :

```js
function addition(a, b) {
  return a + b;
}

let resultat = addition(5, 3);
console.log(resultat); // 8
```

> ⚠️ `return` **interrompt** la fonction dès qu’il est exécuté.

---

## Différence entre `console.log()` et `return`

```js
function ajouter(a, b) {
  console.log(a + b); // affiche le résultat
}

function additionner(a, b) {
  return a + b; // renvoie le résultat
}

ajouter(2, 3); // affiche 5
let somme = additionner(2, 3);
console.log(somme); // 5
```

---

## Exercices

Les exercices [04_fonctions](https://github.com/association-z-code-emploi/exercices-javascript/tree/main/04_fonctions) sont recommandés pour pratiquer les notions vues durant ce cours.
