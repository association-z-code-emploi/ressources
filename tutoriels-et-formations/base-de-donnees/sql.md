---
tags:
  - ressources
  - tutorials
  - basic
---

# SQL

> Ce document n'a pas été conçu comme un guide pour créer du SQL, mais plutôt comme une introduction et une liste de ressources pour apprendre et pratiquer.

SQL, ou "Structured Query Language", est un langage de programmation utilisé pour gérer, interroger et récupérer des données dans une base de onnées relationnelle. C'est un langage utilisé par autant de developpeurs que de non-développeurs (comme des analystes data) pour effectuer des requêtes, manipuler et transformer de la donnée dans une base de ... données ! Parce qu'il est extrêmement simple, les bases de données SQL permettent de stocker efficacement et jusqu'à d'énormes quantités de données, pour des pages ou apps webs.

## Variantes de SQL

Il existe différentes variantes de SQL selon la base de données ou le système de gestion de base de données que l'on choisit.

Ces variantes partagent de nombreuses fonctionalités essentielles, mais ont aussi des différences importantes. Par exemple :

- MySQL est populaire, rapide en lecture, mais il est limité sur des requêtes avancées, plutôt utilisé pour des app web, e-commerces, etc...

- PostgreSQL est robuste, sait prendre en charge des transactions (faire des vérifications complexes avant de confirmer un changement dans la donnée), mais est parfois trop complexe pour de simples sites

- SQLite est ultra-léger (tout tient dans un seul fichier), n'a pas besoin de serveur, mais plutôt fait pour mobiles et pour des structures simples

## Manipulation et maîtrise d'une base de données

Maîtriser SQL (ou une base de données de manière général) ne vient véritablement que par la pratique et l'expérience. On pourra apprendre les basiques autant qu'on le voudra, que ce soit d'un cours, d'un livre, d'une vidéo tuto, etc... ce sont les cas pratiques et concrets qui pousseront à comprendre le besoin et quelle requête effectuer pour répondre au besoin.

Par exemple : on veut récupérer tous les contacts (téléphones et emails) d'une ville en particulier pour diffuser un message d'alerte.

Plusieurs cas de figures :

1.

- qui doit-on récupérer, comme personnes ? -> les personnes d'une ville donnée
- que doit-on récupérer à ces personnes ? -> le numéro de téléphone et l'email de chacune de ces personnes
- il y a-t-il d'autres contraintes ? comme par exemple 1 personne par foyer ? si pas de téléphone et email ?

2.

- que doit-on récupérer ? le numéro de téléphone et l'email de tous le monde
- qui doit-on récupérer, comme personnes ? -> les personnes d'une ville donnée
- il y a-t-il d'autres contraintes ? comme par exemple 1 personne par foyer ? si pas de téléphone et email ?

3.

- que doit-on récupérer ? le numéro de téléphone et l'email de tous le monde, mais 1 personne par foyer ?
- qui doit-on récupérer, comme personnes ? -> les personnes d'une ville donnée
- si pas de téléphone et email ?

4.

- etc...

↳ ces options sont toutes valides, mais on ne traitera pas la donnée de la même manière, dans le même ordre, pas la même quantité de calcul, etc...

Ce ne sera que par la pratique et le besoin que vous saurez ce qui sera le mieux à faire, le plus optimal.

## Si vous avez des difficultés à écrire une requête SQL

1. Faîtes un `SELECT *` pour vérifier que vous avez toute la donnée dont vous avez besoin quelque part
2. Faîtes un `WHERE` pour garder ou retirer la donnée dont vous avez/n'avez pas besoin
3. Changez le `*` par les colonnes dont vous avez besoin. Vous aurez peut-être besoin d'ajouter un `GROUP BY` pour en rassembler, mais ce n'est pas une priorité au début.
4. Ajoutez un `ORDER BY` pour ordonner votre donnée (alphabétique, croissant, etc...)

## Apprendre le SQL

Voici une liste de ressources pour apprendre et surtout pratiquer du SQL :

- [SQL Bolt](https://sqlbolt.com/) : une série de leçons et exercices interactives, en ligne et donc sans installations 🇬🇧
- [SQL ZOO](https://sqlzoo.net/wiki/SQL_Tutorial) : similaire à sqlbolt
- [SQLCourse](https://www.sqlcourse.com/) : cours avec suivi (à faire à son rythme), avec un niveau "débutant" et "avancé"
- [Compétences pratiques du langage SQL](https://www.sql-ex.ru/) : une série d'exercices avec cas pratiques (et tableau des scores, si vous êtes compétitif !)
- [SQL Murder Mystery](https://mystery.knightlab.com/) : "Il y a eu un meutre à SQL City !" Un jeu interactif pour apprendre, avec un cas concret : accumuler de la donnée pour trouver le coupable !
- [Exercices PostgreSQL](https://pgexercises.com/) : une série d'exercices sur une variante de SQL, plus complexe, mais très recherché par les grandes entreprises.
