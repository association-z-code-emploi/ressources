---
tags:
  - tutorials
  - mongo-db
---

# Bases de MongoDB

## Terminologie (vocabulaire)

| **Nom**                     | **Définition**                                               | **Équivalent SQL**             |
| --------------------------- | ------------------------------------------------------------ | ------------------------------ |
| Base de donnée (_database_) | Regroupe les collections                                     | SGBD classique                 |
| Collection                  | Regroupe les documents                                       | Table                          |
| Document                    | Enregistrement individuelle d'une donnée                     | Ligne, mais sans schéma rigide |
| Champ (_Field_)             | Avec une clé et une valeur, dans un document                 | Colonne                        |
| Index                       | Recherche plus rapide dans une collection                    | ------------------------------ |
| Requête (_Query_)           | Récupérer ou filtrer des données                             | "SELECT"                       |
| Curseur (_Cursor_)          | Parcourir les résultats d'une requête, document par document | Pointeur                       |
| Agrégation (_Aggregation_)  | Analyses, résumés, ou transformations de données             | "GROUP BY" / "HAVING"          |

## Types de données

Les données sont donc stockés sous forme de **documents BSON** (une version binaire de JSON), avec chaque **champ** dans un docuement ayant un **type de données spécifique**.

> ℹ️ Ils en existent beaucoup, et voici ci-dessous les plus connus/utilisés.

### ObjectId

Un identifiant unique généré automatiquement pour **identifier chaque document** de façon sûre :

```json
{ "_id": ObjectId("1234567890abcdefghijklmnopqrstuvwxyz")}
```

### String

Pour stocker du **texte** (noms, emails, messages, ...) :

```json
{ "nom": "Jim Feddy" }
```

### Boolean

Pour des valeurs **vraies** (`true`) ou **fausses** (`false`) :

```json
{ "admin": true }
```

### Integer

Pour stocker des **nombres entiers** :

```json
{ "age": 32 }
```

### Double

Pour des **valeurs décimales** (mesures, prix, ...) :

```json
{ "prix": 99.99 }
```

### Date

Pour stocker des **dates** et **heures** :

```json
{ "createdAt": ISODate("2025-05-20T15:10:00Z") }
```

> ℹ️ Utilise la fonction `ISODate()`

### Array

Pour stocker **plusieurs valeurs** dans un seul champ, comme avec des tableaux ou des listes :

```json
{ "tags": ["html", "css", "js", "mongodb"] }
```

> ℹ️ Chaque élément peut être une string, un chiffre ou même un objet !

### Object

Contient un **autre document**, pour organiser des infos liées entre-elles :

```json
{
  "nom": "Jim",
  "adresse": {
    "ville": "Lille",
    "codePostal": "59000"
  }
}
```

### Null

Pour indiquer que la valeur est **absente** ou **inconnue** :

```json
{ "backupEmail": null }
```

## Modèle de données

MongoDB a deux façons d'organiser les données :

- les documents imbriqués pour les relations simples
- les références pour les relations complexes (ie. liés à d'autres collections)

### Documents imbriqués ("_embedded_")

```json
{
  "nom": "Jim",
  "adresse": {
    "ville": "Lille",
    "codePostal": "59000"
  }
}
```

### R2férences ("_normalized_")

```json
{
  "nom": "Jim",
  "adresse": {
    "ville": ObjectId("..."), // qui ferait référence à une collection "Villes" avec toutes les villes à l'intérieur
    "codePostal": "59000"
  }
}
```

> Ces deux façons peuvent être combinées !

## Opérations basiques

### Insertion

```js
// ajouter un document
db.utilisateurs.insertOne({ nom: "Jim", age: 32 });

// ajouter plusieurs documents
db.utilisateurs.insertMany([
  { nom: "Zack", age: 28 },
  { nom: "Sue", age: 30 },
]);
```

### Lecture

```js
// trouver tous les utilisateurs
db.utilisateurs.find();

// trouver un utilisateur par critère
db.utilisateurs.find({ age: { $gt: 25 } }); // "$gt" : plus grand que ...
```

### Mise à jour

```js
// mettre à jour un champ
db.utilisateurs.updateOne({ nom: "Jim" }, { $set: { age: 31 } });
```

### Suppression

#### de donnée

```js
db.utilisateurs.deleteOne({ nom: "Zack" });
```

#### de collection ou de base

```js
db.utilisateurs.drop();
db.dropDatabase();
```

### Index

```js
db.commandes.createIndex({ date: -1 });
```

### Agrégation ("_pipeline_")

```js
db.utilisateurs.aggregate([
  { $match: { age: { $gt: 25 } } },
  { $group: { _id_: "$ville", total: { $sum: 1 } } },
]);
```

---

## Aller plus loin

- [MongoDB CRUD Operations](https://www.mongodb.com/docs/manual/crud/) 📖🇬🇧🇫🇷
- [Data Modeling](https://www.mongodb.com/docs/manual/data-modeling/) 📖🇬🇧🇫🇷
- [Aggregation Operations](https://www.mongodb.com/docs/manual/aggregation/) 📖🇬🇧🇫🇷
