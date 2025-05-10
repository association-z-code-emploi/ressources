---
tags:
  - tutorials
  - laravel
  - php
---

# Routing

La **gestion des routes** (_routing_) permet de définir comment les URL de l’application sont gérées et dirigées vers les contrôleurs appropriés. Les routes sont définies dans le fichier `routes/web.php` pour les requêtes web et `routes/api.php` pour les API.

## Déclaration de base

On peut déclarer facilement une route qui répond à une requête HTTP :

```php
use Illuminate\Support\Facades\Route;

Route::get('/hello', function () {
    return "Hello, World!";
});
```

↳ si un utilisateur visite **http://mon-projet.test/hello**, il verra s'afficher `Hello, World!`

## Object Request

Une **Request** représente une requête HTTP entrante (GET, POST, etc.) et permet de récupérer des données envoyées par un formulaire, une API ou des paramètres d’URL en utilisant l’objet `Illuminate\Http\Request` pour récupérer les données :

```php
use Illuminate\Http\Request;

Route::post('/contact', function (Request $request) {
    $nom = $request->input('nom'); // récupère la valeur de l'input "nom" du formulaire, par exemple "Jim"
    return "Bonjour $nom, votre message a bien été envoyé !"; // → Bonjour Jim, votre message a bien été envoyé !
});
```

Pour récupérer tous les champs envoyés :

```php
Route::post('/contact', function (Request $request) {
    $data = $request->all();
    return response()->json($data);
});
```

Et d'autres méthodes utiles :

- `$request->has('email')` → vérifie si une valeur existe
- `$request->only(['nom', 'email'])` → récupère uniquement certains champs uniquement
- `$request->except(['password'])` → exclut certains champs

## URLs dynamiques

Permet de capturer des segments d’URL pour créer des routes dynamiques :

```php
// par exemple, sur l'URL "/articles/5"
Route::get('/articles/{id}', function ($id) {
    return "Article numéro $id"; // → Article numéro 5
});
```

Il est possible d'avoir valeur par défaut :

```php
// par exemple, sur l'URL "/articles"
Route::get('/articles/{id?}', function ($id = 1) {
    return "Article numéro $id"; // si aucun ID n'est fourni → Article numéro 1
});
```

## Routes nommées

Les routes **nommées** permettent d’associer un nom unique à une route :

```php
Route::get('/dashboard', function () {
    return "Bienvenue sur votre tableau de bord !";
})->name('dashboard');
```

Il est possible de générer une URL depuis une route nommée :

- dans une **view avec Blade** :

```blade
<a href="{{ route('dashboard') }}">Aller à votre tableau de bord</a>
```

- ou dans un **controller** :

```php
return redirect()->route('dashboard');
```

> ℹ️ Les avantages de nommer une route sont :
>
> - de faciliter leur réutilisation : si l’URL de `/dashboard` change plus tard, il suffit de modifier `routes/web.php` sans devoir changer les liens partout dans le code
> - d'être beaucoup plus agréable pour les utilisateurs lorsqu'ils liront l'URL

## Groupes de routes

Permettent d’organiser et d'appliquer des options (préfixes et middlewares) à plusieurs routes en même temps :

```php
Route::prefix('admin')->group(function () {
    Route::get('/dashboard', function () {
        return "Page admin";
    });

    Route::get('/users', function () {
        return "Liste des utilisateurs";
    });
});
```

↳ les URL générées seront :

- `/admin/dashboard`
- `/admin/users`

```php
Route::middleware(['auth'])->group(function () {
    Route::get('/profil', function () {
        return "Page protégée : il s'agit d'un profil utilisateur";
    });
});
```

↳ seuls les utilisateurs connectés auront accès à `/profil` !

---

## Exercices

Les exercices suivants sont recommandés pour ce cours-ci :

- [TBA](#) 🚧
