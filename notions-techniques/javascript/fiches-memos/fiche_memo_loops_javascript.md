---
tags:
  - tutorials
  - cheatsheets
  - javascript
---

# Fiche mémo : boucles ("loops") en JavaScript

## `for`

```js
for (let i = 0; i < 5; i++) {
  console.log(i);
}
// Affichera : 0 1 2 3 4
```

> ℹ️ Documentation sur [MDN](https://developer.mozilla.org/fr/docs/Web/JavaScript/Reference/Statements/for)

---

## `while`

```js
let iterator = 0;
while (iterator < 5) {
  iterator++;
  console.log(iterator);
}
// Affichera : 1 2 3 4 5
```

> ℹ️ Documentation sur [MDN](https://developer.mozilla.org/fr/docs/Web/JavaScript/Reference/Statements/while)

---

## `for...in`

```js
const arr = [3, 5, 7];
for (let i of arr) {
  console.log(i);
}
// Affichera : 3 5 7
```

> ℹ️ Documentation sur [MDN](https://developer.mozilla.org/fr/docs/Web/JavaScript/Reference/Statements/for...in)

---

## `do...while`

```js
let iterator = 0;
do {
  iterator++;
  console.log(iterator);
} while (iterator < 5);
// Affichera : 1 2 3 4 5
```

> ℹ️ Documentation sur [MDN](https://developer.mozilla.org/fr/docs/Web/JavaScript/Reference/Statements/do...while)
