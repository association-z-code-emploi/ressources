---
tags:
  - tutorials
  - cheatsheets
  - javascript
---

# Fiche mémo : conditions en JavaScript

> ℹ️ Documentation sur [MDN](https://developer.mozilla.org/fr/docs/Web/JavaScript/Reference/Statements/if...else)

## `if`

```js
const trafficLight = "Yellow";

if (trafficLight === "Green") {
  console.log("Go!");
}
console.log("After green if");

if (trafficLight === "Yellow") {
  console.log("Slow down!");
}
console.log("After yellow if");

if (trafficLight === "Red") {
  console.log("Stop!");
}
console.log("After red if");

/* Affichera :
After green if
Slow down!
After yellow if
After red if
*/
```

---

## `if...else if`

```js
const trafficLight = "Yellow";

if (trafficLight === "Green") {
  console.log("Go!");
} else if (trafficLight === "Yellow") {
  console.log("Slow down!");
} else if (trafficLight === "Red") {
  console.log("Stop!");
}
console.log("After if...else if");

/* Affichera :
Slow down!
After if...else if
*/
```

---

## `if...else if...else`

```js
const trafficLight = "Blue";

if (trafficLight === "Green") {
  console.log("Go!");
} else if (trafficLight === "Yellow") {
  console.log("Slow down!");
} else if (trafficLight === "Red") {
  console.log("Stop!");
} else {
  console.log("Invalid light.");
}
console.log("After if...else if...else");

/* Affichera :
Invalid light.
After if...else if...else
*/
```
