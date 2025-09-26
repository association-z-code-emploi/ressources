---
tags:
  - tutorials
  - cheatsheets
  - javascript
  - dom
---

# Fiche mémo : événements ("events") en JavaScript (DOM)

> ℹ️ Documentation sur [MDN](https://developer.mozilla.org/fr/docs/Web/Events)

## `click` — quand l’utilisateur clique avec sa souris

```js
const button = document.querySelector("button");

button.addEventListener("click", () => {
  console.log("Button clicked!");
});
```

---

## `mouseover` — quand l’utilisateur passe la souris sur un élément

```js
const box = document.querySelector(".box");

box.addEventListener("mouseover", () => {
  console.log("The mouse is hovering the box!");
});
```

---

## `keydown` — quand une touche du clavier est appuyée

```js
document.addEventListener("keydown", (event) => {
  console.log(`Key down : ${event.key}`);
});
```

---

## `change` — quand un input (formulaire) change

```js
const input = document.querySelector("input");

input.addEventListener("change", () => {
  console.log("Updated value :", input.value);
});
```

---

## `submit` — quand un formulaire est envoyé

```js
const form = document.querySelector("form");

form.addEventListener("submit", (event) => {
  event.preventDefault(); // empêche le rechargement
  console.log("Form submitted!");
});
```

---

## `load` — quand la page est complètement chargée

```js
window.addEventListener("load", () => {
  console.log("Page fully loaded!");
});
```
