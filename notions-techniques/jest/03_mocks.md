---
tags:
  - tutorials
  - jest
  - javascript
---

> Tiré de la [documentation officielle de Jest](https://archive.jestjs.io/docs/en/mock-functions)

# Les fonctions "mockées"

Les **mocks** permettent de simuler des appels à des API sans vraiment les exécuter, de tester des fonctions sans dépendre d'une base de données ou d'un fichier externe ou encore de vérifier combien de fois une fonction est appelée et avec quels arguments.

## Syntaxe et utilisation

On créé une **fonction mockée** avec `jest.fn()` :

```javascript
const mockFunction = jest.fn(); // créé une fonction simulée

mockFunction(); // appel de la fonction

test("mockFunction est appelée", () => {
  expect(mockFunction).toHaveBeenCalled(); // on vérifie qu'elle a bien été appelée
});
```

On peut aussi vérifier **combien de fois** elle a été appelée :

```javascript
test("mockFunction est appelée exactement 1 fois", () => {
  expect(mockFunction).toHaveBeenCalledTimes(1);
});
```

Et on peut aussi voir **avec quels arguments** elle a été appelée :

```javascript
const mockFunction = jest.fn();
mockFunction("toto", 42);

test("mockFunction reçoit les arguments attendus", () => {
  expect(mockFunction).toHaveBeenCalledWith("toto", 42);
});
```

## La propriété `.mock`

Chaque fonction mockée possède une propriété `.mock` qui stocke des infos utiles sur son exécution :

```javascript
const mockFunction = jest.fn();

mockFunction("test1");
mockFunction("test2");

test("combien de fois le mock a été appelé", () => {
  console.log(mockFunction.mock.calls.lenght); // 2
});

test("quels sont les résultats des différents appels du mock", () => {
  console.log(mockFunction.mock.results[0].value); // 'test1'
  console.log(mockFunction.mock.results[1].value); // 'test2'
});

// etc...
```

## Modifier les valeurs retournées par un mock

Une fonction mockée ne fait **rien** par défaut, mais on peut lui assigner une valeur de retour avec `mockReturnValue()` :

```javascript
const mockFunction = jest.fn().mockReturnValue("fake data");

test("mockFunction retourne une donnée simulée", () => {
  expect(mockFunction()).toBe("fake data");
});
```

On peut aussi faire varier la valeur retournée à chaque appel :

```javascript
const mockFunction = jest
  .fn()
  .mockReturnValueOnce("premier appel")
  .mockReturnValueOnce("deuxième appel");

test("valeurs retournées sur plusieurs appels", () => {
  expect(mockFunction()).toBe("premier appel");
  expect(mockFunction()).toBe("deuxième appel");
  expect(mockFunction()).toBe(undefined); // aucun mockReturnValueOnce restant !
});
```

> Si la fonction est appelée une troisième fois, elle retournera `undefined` car il n’y a plus d'aassignation définie.

## "Mocker" un fichier/module entier

Par exemple, le fichier/module `math.js` contient une fonction `addition` :

```javascript
// math.js
export function addition(a, b) {
  return a + b;
}
```

On peut le mocker dans un test :

```javascript
jest.mock("./math", () => ({
  addition: jest.fn().mockReturnValue(10),
}));

import math from "math.js";

test("l'addition mockée doit retourner 10", () => {
  expect(math.addition(2, 3)).toBe(10);
});
```

> ℹ️ Quand on utilise `jest.mock()`, toutes les fonctions du module sont **mockées** par défaut. Si on veut rétablir le comportement original, on peut utiliser `jest.requireActual()` !

## `jest.fn` et `mockImplementationOnce`

Il existe des cas où il utilise d'**écrire sa propre implémentation** pour une fonction mockée avec `mockImplementation()` :

```javascript
const mockFunction = jest.fn((a, b) => a * b);

test("mockFunction multiplie les nombres", () => {
  expect(mockFunction(2, 3)).toBe(6);
});
```

Comme avec `mockReturnValueOnce`, on peut aussi définir une implémentation **valable une seule fois** avec `mockImplementationOnce()` :

```javascript
const mockFunction = jest
  .fn()
  .mockImplementationOnce((a, b) => a + b)
  .mockImplementationOnce((a, b) => a * b);

test("différentes implémentations", () => {
  expect(mockFunction(2, 3)).toBe(5); // addition
  expect(mockFunction(2, 3)).toBe(6); // multiplication
  expect(mockFunction(2, 3)).toBe(undefined); // aucun mockImplementationOnce restant !
});
```

> Si la fonction est appelée une troisième fois, elle retournera `undefined` car il n’y a plus d’implémentation définie.

---

## Exercices

Les exercices suivants sont recommandés pour ce cours-ci :

- [TBA](#) 🚧
