---
tags:
  - tutorials
  - jest
  - javascript
---

> Tiré de la [documentation officielle de Jest](https://archive.jestjs.io/docs/en/getting-started)

# Introduction à Jest

Jest est un framework open-source populaire de test **JavaScript**, développé par Facebook. Il est conçu pour être simple d'utilisation en intégrant des fonctionnalités comme :

- une exécution rapide des tests, et en simultanés les uns les autres
- néanmoins des tests isolés et faciles à écrire
- une prise en charge des tests asynchrones (promesses, API, Timeout, etc...)
- des fonctionnalités avancées comme les mocks et snapshots

## Installation et configuration

Jest est compatible avec **Node.js** et s’installe facilement via _npm_ ou _yarn_ :

```shell
# avec npm
npm install --save-dev jest

# avec yarn
yarn add --dev jest
```

Il suffit ensuite d'ajouter un script dans le `package.json` pour exécuter Jest :

```json
{
  "scripts": {
    "test": "jest"
  }
}
```

## Écrire son premier test

Créez un fichier de test `sum.test.js` :

```javascript
test("additionne 1 + 2 et retourne 3", () => {
  expect(1 + 2).toBe(3);
});
```

Lancez les tests :

```shell
# avec npm
npm run test

# avec yarn
yarn test
```

Jest détectera automatiquement les fichiers de test et exécutera le test défini.

---

## Exercices

Les exercices suivants sont recommandés pour ce cours-ci :

- [TBA](#) 🚧
