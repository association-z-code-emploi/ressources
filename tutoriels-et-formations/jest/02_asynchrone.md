---
tags:
  - tutorials
  - jest
  - javascript
---

> Tiré de la [documentation officielle de Jest](https://archive.jestjs.io/docs/en/asynchronous)

# Tester du code asynchrone

Il est courant d’écrire du code asynchrone en JavaScript avec des **promesses** et `async/await`. Jest propose plusieurs façons de tester ce type de code.

## Tester les promesses

Exemple avec une fonction asynchrone qui retourne une **promesse** :

```javascript
function fetchData() {
  return new Promise((resolve) => {
    setTimeout(() => resolve("Données récupérées"), 1000);
  });
}

test("fetchData retourne les bonnes données", () => {
  return fetchData().then((data) => {
    expect(data).toBe("Données récupérées");
  });
});
```

> ⚠️ Il faut **retourner** la promesse dans `test()`, sinon Jest risque de ne pas attendre la fin du test et de le marquer comme réussi trop tôt !

### `.resolves` et `.rejects`

Pour tester plus simplement les promesses, Jest propose des **matchers spécifiques** lors qu'une promesse réussit ou échoue.

```javascript
test("fetchData réussi et retourne les bonnes données", () => {
  return expect(fetchData()).resolves.toBe("Données récupérées");
});
```

```javascript
function fetchDataWithError() {
  return new Promise((_, reject) => {
    setTimeout(() => reject(new Error("Accès limité")), 1000);
  });
}

test("fetchData échoue et renvoie une erreur", () => {
  return expect(fetchDataWithError()).rejects.toThrow("Accès limité");
});
```

## `async/await`

Jest supporte nativement `async/await`, de la même manière qu'avec des promesses "classiques".

On peut **attendre** la fin de l’exécution avec `await` :

```javascript
test("fetchData réussi et retourne les bonnes données", async () => {
  const data = await fetchData();
  expect(data).toBe("Données récupérées");
});
```

```javascript
test("fetchData échoue et renvoie une erreur", async () => {
  await expect(fetchDataWithError()).rejects.toThrow("Accès limité");
});
```

Ou avec `try/catch` :

```javascript
test("fetchData échoue et renvoie une erreur en la catchant", async () => {
  try {
    await fetchDataWithError();
  } catch (error) {
    expect(error).toBeInstanceOf(Error);
    expect(error.message).toBe("Accès limité");
  }
});
```

---

## Exercices

Les exercices suivants sont recommandés pour ce cours-ci :

- [TBA](#) 🚧
