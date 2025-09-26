---
tags:
  - tutorials
  - cheatsheets
  - javascript
---

# Fiche mémo : fonctions ("functions") en JavaScript

> ℹ️ Documentation des fonctions sur [MDN](https://developer.mozilla.org/fr/docs/Web/JavaScript/Guide/Functions)

## Fonction nommée

```js
function myFunction() {
  console.log("Hello, World!");
}

myFunction(); // Affichera : Hello, World!
```

---

## Fonction nommée avec paramètres

```js
function myFunction(myParameter) {
  console.log(myParameter);
}

myFunction(5); // Affichera : 5
```

---

## Fonction anonyme

```js
const myFunction = function () {
  console.log("Hello, World!");
};

myFunction(); // Affichera : Hello, World!
```

---

## Fonction anonyme avec paramètres

```js
const myFunction = function (myParameter) {
  console.log(myParameter);
};

myFunction(5); // Affichera : 5
```

---

## Fonction fléchée

```js
const myFunction = () => {
  console.log("Hello, World!");
};

myFunction(); // Affichera : Hello, World!
```

---

## Fonction fléchée avec paramètres

```js
const myFunction = (myParameter) => {
  console.log(myParameter);
};

myFunction(5); // Affichera : 5
```

---

## Fonction concise (une seule instruction dans la fonction)

```js
const myFunction = (myParameter) => console.log(myParameter);

myFunction(5); // Affichera : 5
```
