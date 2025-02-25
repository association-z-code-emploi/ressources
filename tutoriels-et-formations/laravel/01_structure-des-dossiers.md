---
tags:
  - tutorials
  - laravel
  - php
---

# Structure des dossiers

Laravel a une structure organisée en plusieurs dossiers pour séparer les différentes fonctionnalités de l’application.

## Structure de base

```txt
/mon-projet
│── app/
│   ├── Console/         # commandes "artisan" personnalisées
│   ├── Exceptions/      # gère les erreurs
│   ├── Http/
│   │   ├── Controllers/ # controllers : logique métier
│   │   ├── Middleware/  # middlewares des requêtes HTTP
│   ├── Models/          # Models
│── bootstrap/           # fichiers d'initialisation
│── config/              # configuration de Laravel (eg. "database.php")
│── database/            # migrations et factories
│── public/              # point d’entrée de l’application ("index.php")
│── resources/           # fichiers front-end (views, CSS, JS, images, etc...)
│   ├── views/           # templates Blade (ex: "articles/index.blade.php")
│── routes/              # définitions des routes (eg. "web.php", "api.php", etc...)
│── storage/             # logs et cache
│── tests/               # tests unitaires et fonctionnels
│── vendor/              # dépendances installées via Composer
```

## Les dossiers les plus importants :

- **`app/Http/Controllers/`** : les contrôleurs pour gérer les requêtes
- **`app/Models/`** : les modèles représentant les tables de la base de données
- **`resources/views/`** : les fichiers templates pour l'affichage (ie. Blade)
- **`routes/web.php`** : définit les routes de l’application

> 🛠️ Laravel fournit la commande artisan suivante pour créer un modèle avec sa migration :
>
> ```shell
> php artisan make:model Article -m
> ```
>
> ↳ génère un **model** dans `app/Models/Article.php` et une **migration** dans `database/migrations/`

---

## Exercices

Les exercices suivants sont recommandés pour ce cours-ci :

- [TBA](#) 🚧
