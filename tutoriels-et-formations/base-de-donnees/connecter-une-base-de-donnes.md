---
tags:
  - ressources
  - tutorials
  - advanced
---

# Connecter une base de données

> ℹ️ Les exemples utilisés seront pour PHP et MySQL

> ⚠️ Des variations du code ci-dessous peuvent être nécessaires, selon les outils que vous utilisez (XAMPP, WAMP, MAMP, etc...)

## Pourquoi structurer une base dès le début d'un projet ?

- On réduit les risques de devoir refaire ou corriger des parties importantes de la structure de la base de données
- On améliore les performances : une base de données optimisée répond plus rapidement aux requêtes

## Dans la pratique

> ⚠️ Avant de tester ce code, assurez-vous d'avoir une base de données créée et accessible à partir de l'outil de votre choix (phpMyAdmin, CLI, etc...)

```php
<?php
try {
    // ↓ connexion à la base de données ; on remplacera "ma-base" par le nom de la base de donnée
    $dsn = 'mysql:host=localhost;dbname=ma-base;charset=utf8';

    $username = 'root'; // ← votre nom d'utilisateur

    $password = ''; // ← votre mot de passe (souvent vide en local, comme ici dans l'exemple)

    // ↓ PDO est une extension intégrée à PHP qui permet d'interagir avec une base de données comme avec des objets
    $pdo = new PDO($dsn, $username, $password);

    // ↓ configuration des options PDO
    $pdo->setAttribute(PDO::ATTR_ERRMODE, PDO::ERRMODE_EXCEPTION);

    // ↓ un simple message pour confirmer (ou pas) la connexion
    echo "Connexion réussie !";

} catch (PDOException $e) {
    // ↓ un autre message, mais en cas d'erreur ; celui d'avant ("Connexion réussie") ne s'affichera alors pas
    die("Erreur de connexion : " . $e->getMessage());
}
?>
```

---

## Aller plus loin

- [Manuel officiel de PHP sur la PDO](https://www.php.net/manual/fr/book.pdo.php) 🇫🇷
