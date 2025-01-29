---
tags:
  - ressources
  - tutorials
  - advanced
---

# L'architecture MVC

- **MVC** signifie **Modèle - Vue - Contrôleur**.
- il s'agit d'une architecture (une construction de l'ensemble du code) qui sépare les responsabilités d'une application :
  - **modèle (model)** : gestion des données (base de données, logique métier, etc...)
  - **vue (view)** : affichage (HTML, interface utilisateur, etc...)
  - **contrôleur (controller)** : lien entre les modèles et les vues (logique d'application)

Cela permet de :

1. **séparer les responsabilités** : le code est plus facile à maintenir et à faire évoluer/mettre à jour

   ↳ imaginez qu'un pneu de votre voiture serait directement relier au système des vitres : si le pneu crève, alors la vitre aussi (et probablement tout le reste), ce qui est loin d'être idéal !

2. **d'être plus lisible** : chaque "couche" a un rôle clair et précis

   ↳ on va séparer le code en différents fichiers, donc pas ou peu de chances de ne pas facilement s'y retrouver

3. **à réutiliser le code** : les vues peuvent être réutilisées avec d'autres contrôleurs

   ↳ une même page peut afficher différentes informations selon l'utilisateur, ses droits, etc... on va alors pouvoir afficher contextuellement telle ou telle donnée

## Structure des dossiers MVC

### Arborescence d'un projet

Voici un exemple d'arborescence de projet en PHP :

```text
- /app
  - /controllers
    - HomeController.php
  - /models
    - UserModel.php
  - /views
    - homepage.php
- /public
  - index.php
```

- **/app** : contient tous les fichiers principaux du projet
  - **/controllers** : les contrôleurs
  - **/models** : les modèles
  - **/views** : les fichiers d'affichage (pour le rendu)
- **/public** : le point d'entrée de l'application (ce qui sera accessible via le navigateur)

### Sous-parties du MVC

#### Controller

> dans `/app/controllers/HomeController.php`

```php
<?php
class HomeController {
    public function index() {
        $data = ["title" => "Hello, World!"];

        require_once '../app/views/homepage.php';
    }
}
```

#### View

> dans `/app/views/homepage.php`

```php
<!DOCTYPE html>
<html>
<body>
    <h1><?= $data['title']; ?></h1>
</body>
</html>
```

#### Public

> dans `/public/index.php`

```php
<?php
require_once '../app/controllers/HomeController.php';

$controller = new HomeController();
$controller->index();
```

#### Model

> dans `/app/models/UserModel.php`

```php
<?php
class UserModel {
    public function getUsers() {
        return [
            ["id" => 1, "name" => "Alice"],
            ["id" => 2, "name" => "Bob"]
        ];
    }
}
```

#### Controller + Model

> dans `/app/controllers/HomeController.php`

```php
<?php
require_once '../app/models/UserModel.php';

class HomeController {
    public function index() {
        $userModel = new UserModel();
        $users = $userModel->getUsers();

        $data = [
            "title" => "Liste des utilisateurs",
            "users" => $users
        ];

        require_once '../app/views/homepage.php';
    }
}
```

#### View avec une boucle

> dans `/app/views/homepage.php`

```php
<!DOCTYPE html>
<html>
<head>
    <title><?= $data['title']; ?></title>
</head>
<body>
    <h1><?= $data['title']; ?></h1>
    <ul>
        <?php foreach ($data['users'] as $user): ?>
            <li><?= $user['name']; ?></li>
        <?php endforeach; ?>
    </ul>
</body>
</html>
```

---

## Récapitulatif

1. **Un rôle par fichier** :
   - le contrôleur **contrôle** l'ensemble
   - le modèle **gère les données**
   - la vue **affiche les données**
2. **Pas de logique métier dans les vues** (on ne vérifie pas dans une vue que seul un admin peut lire une page, par exemple)
3. **C'est le contrôleur qui appelle les modèles et les vues**
