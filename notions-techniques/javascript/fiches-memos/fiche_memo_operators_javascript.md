---
tags:
  - tutorials
  - cheatsheets
  - javascript
---

# Fiche mémo : opérateurs en JavaScript

> ℹ️ Pour la liste complète et à jour, consultez la liste des opérateurs sur [MDN](https://developer.mozilla.org/fr/docs/Web/JavaScript/Reference/Operators/Addition#voir_aussi).

| **Opérateur** | **Description** | **Exemple** |
| ------------- | --------------- | ----------- |
| `+`           | Addition (ou concaténation avec des strings)                                         | `5 + 3 // 8`, `"Hello " + "World" // "Hello World"` |
| `-`           | Soustraction                                                                         | `10 - 4 // 6`                                       |
| `*`           | Multiplication                                                                       | `6 * 2 // 12`                                       |
| `/`           | Division                                                                             | `10 / 2 // 5`                                       |
| `%`           | Modulo (reste de la division)                                                        | `10 % 3 // 1`                                       |
| `**`          | Exponentiation                                                                       | `2 ** 3 // 8`                                       |
| `++`          | Incrémentation (augmente de 1)                                                       | `let x = 5; x++; // 6`                              |
| `--`          | Décrémentation (diminue de 1)                                                        | `let y = 5; y--; // 4`                              |
| `=`           | Affectation                                                                          | `let a = 10;`                                       |
| `+=`          | Addition et affectation                                                              | `let a = 5; a += 3; // 8`                           |
| `-=`          | Soustraction et affectation                                                          | `let a = 5; a -= 2; // 3`                           |
| `*=`          | Multiplication et affectation                                                        | `let a = 5; a *= 2; // 10`                          |
| `/=`          | Division et affectation                                                              | `let a = 10; a /= 2; // 5`                          |
| `%=`          | Modulo et affectation                                                                | `let a = 7; a %= 3; // 1`                           |
| `==`          | Égalité (conversion de type possible)                                                | `5 == "5" // true`                                  |
| `===`         | Égalité stricte (pas de conversion de type)                                          | `5 === "5" // false`                                |
| `!=`          | Différent (conversion de type possible)                                              | `5 != "5" // false`                                 |
| `!==`         | Différent strict (pas de conversion de type)                                         | `5 !== "5" // true`                                 |
| `>`           | Supérieur à                                                                          | `8 > 3 // true`                                     |
| `<`           | Inférieur à                                                                          | `2 < 5 // true`                                     |
| `>=`          | Supérieur ou égal à                                                                  | `5 >= 5 // true`                                    |
| `<=`          | Inférieur ou égal à                                                                  | `3 <= 2 // false`                                   |
| `&&`          | ET logique (retourne le premier `false` ou le dernier `true`)                        | `true && false // false`, `5 && 10 // 10`           |
| `\|\|`| OU logique (retourne le premier `true` ou le dernier `false`) | `false \|\| true // true`, `0 \|\| "Hello" // "Hello"` |
| `!`           | NON logique                                                                          | `!true // false`                                    |
| `??`          | "Nullish coalescing" (retourne la 1ère valeur définie, ignore `null` et `undefined`) | `null ?? "default" // "default"`                    |
| `?:`          | Opérateur ternaire (condition)                                                       | `let age = 18; let res = age >= 18 ? "ok" : "no";`  |
