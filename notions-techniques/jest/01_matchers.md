---
tags:
  - tutorials
  - jest
  - javascript
---

> Tiré de la [documentation officielle de Jest](https://archive.jestjs.io/docs/en/using-matchers)

# Les matchers

Jest utilise des **matchers** pour comparer/vérifier différents types de valeurs, comme des nombres, des chaînes de caractères, des tableaux, et bien plus encore !

## Matchers communs

### `toBe(value)`

Vérifie une égalité stricte (similaire à `===` en JavaScript) :

```javascript
test("2 est strictement égal à 2", () => {
  expect(2).toBe(2);
});
```

### `toEqual(value)`

Compare le contenu des objets ou des tableaux (contrairement à `toBe` qui compare uniquement des références) :

```javascript
test("objet contenant les mêmes propriétés", () => {
  const data = { one: 1 };
  data.two = 2;
  expect(data).toEqual({ one: 1, two: 2 });
});
```

### `toBeNull()`

```javascript
test("variable est null", () => {
  const data = null;
  expect(data).toBeNull();
});
```

### `toBeUndefined()`

```javascript
test("variable est undefined", () => {
  const data = undefined;
  expect(data).toBeUndefined();
});
```

### `toBeDefined()`

```javascript
test("variable n'est pas undefined", () => {
  const data = 42;
  expect(data).toBeDefined();
});
```

### `toBeTruthy` et `toBeFalsy`

```javascript
test("null est falsy", () => {
  expect(null).toBeFalsy();
});

test("0 est falsy", () => {
  expect(0).toBeFalsy();
});

test("une chaîne non vide est truthy", () => {
  expect("hello").toBeTruthy();
});
```

### `not` pour inverser un test

```javascript
test("valeur non égale à ...", () => {
  expect(5).not.toBe(3);
});
```

## Comparer des nombres

Jest propose aussi plusieurs matchers pour comparer des nombres :

```javascript
test("comparaison de nombres", () => {
  const value = 10;
  expect(value).toBeGreaterThan(5);
  expect(value).toBeGreaterThanOrEqual(10);
  expect(value).toBeLessThan(20);
  expect(value).toBeLessThanOrEqual(10);
});
```

> ⚠️ Pour les nombres flottants (eg. "3.14"), il vaut mieux utiliser `toBeCloseTo()` à la place de `toEqual()` à cause des imprécisions d’arrondi.

```javascript
test("les nombres à virgule flottante", () => {
  expect(0.1 + 0.2).toBeCloseTo(0.3); // évite les erreurs d'arrondi !
});
```

## Comparer des chaînes de caractères (string)

Évidemment, Jest permet de vérifier si une chaîne de caractères contient une sous-chaîne spécifique grâce à `toMatch()` :

```javascript
test("la string contient un mot spécifique", () => {
  expect("hello world").toMatch(/world/);
});
```

## Comparer des tableaux

```javascript
test("le tableau contient un élément spécifique", () => {
  const langages = ["javascript", "php", "python"];
  expect(langages).toContain("php");
});
```

```javascript
test("deux tableaux identiques", () => {
  expect([1, 2, 3]).toEqual([1, 2, 3]);
});
```

## Vérifier les exceptions (`toThrow`)

Quand une fonction est censée générer une erreur, on peut tester cela avec `toThrow()` :

```javascript
function divisionParZero() {
  throw new Error("Division par zéro interdite !");
}

test("vérifier si une erreur est relevée", () => {
  expect(() => divisionParZero()).toThrow();
});

test("vérifier un message d’erreur spécifique", () => {
  expect(() => divisionParZero()).toThrow("Division par zéro interdite !");
});
```

---

## Exercices

Les exercices suivants sont recommandés pour ce cours-ci :

- [TBA](#) 🚧
