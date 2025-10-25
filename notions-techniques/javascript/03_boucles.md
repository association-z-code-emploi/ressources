---
tags:
  - tutorials
  - javascript
---

# Boucles

Les **boucles** permettent de **répéter du** code tant qu’une condition est **vraie**.

On trouve trois variations :

- `while`
- `for`
- `for...of`

---

## "Tant que ..." : `while`

```js
let i = 1;
while (i <= 5) {
  console.log(`Tour n°${i}`);
  i++;
}
```

---

## "Autant de fois que ..." : `for`

```js
for (let i = 1; i <= 5; i++) {
  console.log(`Tour n°${i}`);
}
```

---

## Boucle + tableau : `for...of`

Pour parcourir un tableau :

```js
let notes = [12, 5, 7];

for (let note of notes) {
  console.log(note);
}
```

---

> ℹ️ Dans le cours suivant, vous découvrirez les [fonctions](./04_fonctions.md) pour répéter une instruction et la réutiliser !

---

## Exercices

Les exercices [03_boucles](https://github.com/association-z-code-emploi/exercices-javascript/tree/main/03_boucles) sont recommandés pour pratiquer les notions vues durant ce cours.
