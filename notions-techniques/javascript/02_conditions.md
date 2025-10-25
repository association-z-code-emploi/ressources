---
tags:
  - tutorials
  - javascript
---

# Conditions

Les conditions exécutent du code **si un test est vrai** :

```js
let temperature = 17;

if (temperature > 30) {
  console.log("Il fait chaud !");
} else {
  console.log("Il fait frais !");
}
```

On peut ajouter des `else if` pour d’autres cas :

```js
let temperature = 22;

if (temperature > 30) {
  console.log("Il fait chaud !");
} else if (temperature >= 20) {
  console.log("Il fait bon !");
} else {
  console.log("Il fait frais !");
}
```

---

### Comparateurs

| Symbole | Signification         |
| ------- | --------------------- |
| `==`    | égal à (valeur)       |
| `===`   | strictement égal      |
| `!=`    | différent de          |
| `!==`   | strictement différent |
| `>`     | supérieur à           |
| `<`     | inférieur à           |
| `>=`    | supérieur ou égal à   |
| `<=`    | inférieur ou égal à   |

> ⚠️ `===` est recommandé : il compare **valeur et type**
> Exemple :
>
> ```js
> 5 == "5"; // true
> 5 === "5"; // false
> ```

---

### Opérateurs logiques

| Opérateur | Signification |
| --------- | ------------- |
| `&&`      | "et" logique  |
| `\|\|`    | "ou" logique  |
| `!`       | "non" logique |

```js
let age = 20;
let sobre = true;

if (age >= 18 && sobre) {
  console.log("Vous pouvez entrer !");
}
```

---

> ℹ️ Dans le cours suivant, vous découvrirez les [boucles](./03_boucles.md) pour répéter une exécution !

---

## Exercices

Les exercices [02_conditions](https://github.com/association-z-code-emploi/exercices-javasxcript/tree/main/02_conditions) sont recommandés pour pratiquer les notions vues durant ce cours.
