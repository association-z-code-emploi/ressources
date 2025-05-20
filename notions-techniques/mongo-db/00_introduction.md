---
tags:
  - tutorials
  - mongo-db
---

# Introduction à MongoDB

**MongoDB** est une **base de données NoSQL** **open-source** et **orientée documents**. Contrairement aux bases SQL (comme MySQL), MongoDB n'**utilise pas de tables rigides** avec des lignes et colonnes, mais des documents JSON plus **flexibles**, faciles à adapter à diofférents types de données.

Reprenons ses caractéristiques :

- **orienté documents** :

Les données sont stockées sous forme de documents JSON (en fait BSON, c'est à dire du JSON binaire) :

```json
{
  "_id": 1,
  "nom": "Jim",
  "email": "jim@mail.fed"
}
```

- **schéma flexibles** :

Chaque document peut avoir des champs différents. Pas besoin de modifier la structure entière pour ajouter une nouvelle info.

- **indexation et agrégation** :

Pour **accélérer les recherches**, on peut indexer les champs :

```js
db.utilisateurs.createIndex({ email: 1 });
```

On peut aussi **filtrer**, **transformer** ou **grouper** les données, comme avec SQL.

## SQL vs NoSQL

| **SQL** (relationel)        | **NoSQL** (eg: MongoDB)          |
| --------------------------- | -------------------------------- |
| Données en tables           | Données en documents JSON        |
| Schéma fixe                 | Schéma souple                    |
| Requêtes SQL complexes      | Requêtes plus simples en JSON    |
| Bonne cohérence des données | Haute performance et flexibilité |

---

## Aller plus loin

- [NoSQL vs SQL Databases](https://www.mongodb.com/fr-fr/resources/basics/databases/nosql-explained/nosql-vs-sql) 📖🇬🇧🇫🇷
- [Feed NoSQL](https://app.daily.dev/tags/nosql?ref=roadmapsh) 📖🇬🇧
- [Getting Started with MongoDB](https://www.mongodb.com/docs/manual/tutorial/getting-started/) 🎞️🇬🇧
