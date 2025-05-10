---
tags:
  - tutorials
  - laravel
  - php
---

# Introduction à Laravel

Laravel est un **framework PHP** open-source conçu pour rendre le développement d'applications web plus fluide et efficace, notamment la logique métier d'une application. Il suit l'architecture **MVC (Modèle - Vue - Contrôleur)** et offre une syntaxe permettant de simplifier des tâches courantes telles que :

- la gestion des routes
- l'accès aux bases de données avec **Eloquent ORM**
- l'authentification et la gestion des utilisateurs
- les migrations et les factories
- l'utilisation d'un moteur de template avec **Blade**
- l'intégration avec des API et services tiers
- et d'autres !

> ℹ️ "La logique métier est un ensemble de règles et de processus qui régissent les opérations de l’application. Elle est utilisée pour décrire les étapes nécessaires pour accomplir une tâche particulière, ainsi que ses règles et conditions pour que cette tâche soit considérée comme terminée avec succès." - _source : [SuperForge](https://www.superforge.io/articles/logique-metier-application)_

## Laravel et l'architecture MVC

Laravel suit **le modèle MVC** (**Modèle - Vue - Contrôleur**) : une séparation des responsabilités facilitant le développement et la maintenance du code.

La structure est la suivante :

1. **Modèle (Model)** : gère la logique métier et les interactions avec la base de données
2. **Vue (View)** : gère l'affichage et l'interface utilisateur, en utilisant un moteur de templates
3. **Contrôleur (Controller)** : fait le lien entre le **Modèle** et la **Vue**, traite les requêtes et renvoie les réponses

**Exemple** :

1. Un utilisateur visite `/articles`
2. La requête passe par **routes/web.php** pour être dirigée vers un contrôleur
3. Le **Controller** récupère les données de l'article via un **Model**
4. Les données sont envoyées à une **View** qui les affiche aux yeux de l'utilisateur

> 🛠️ Laravel propose une commande pour générer un contrôleur !
>
> ```shell
> php artisan make:controller MonControlleur
> ```

---

## Exercices

Les exercices suivants sont recommandés pour ce cours-ci :

- [TBA](#) 🚧
