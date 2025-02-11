---
tags:
  - tutorials
  - advanced
---

# CRUD

> ℹ️ Les exemples utilisés seront pour PHP et MySQL

CRUD est un acronyme pour **Create, Read, Update, Delete** : il représente les 4 opérations de base qu’on peut effectuer sur une base de données. Elles sont utiles pour beaucoup d'opérations, comme la gestion d’utilisateurs, la création d'articles, etc... C'est aujourd'hui un modèle bien connu et très utilisé.

Cela permet de :

- gérer plus facilement les données dans une application
- d'avoir une structure logique et plus facile à implémenter dans un projet

## Dans la pratique

> ⚠️ Pensez à d'abord connecter votre base de donnée et ajouter son code dans votre fichier, avant les exemples ci-dessous. Si vous ne savez pas comment connecter une base de données, référez-vous à l'article "[Connecter une base de données [en SQL]](../base-de-donnees/connecter-une-base-de-donnes.md)"

## CREATE (créer)

↳ ajouter une nouvelle entrée dans la base de données

### Exemple

```php
<?php
// n'oubliez pas de faire votre connexion à la base de données ici, avant les commandes ci-dessous

$sql = "INSERT INTO utilisateurs (nom, email) VALUES (:nom, :email)";

$stmt = $pdo->prepare($sql);

$stmt->execute([
    ':nom' => 'Flo Z.',
    ':email' => 'flo.z@example.mail',
]);

echo "Utilisateur ajouté avec succès !";
?>
```

## READ (lire)

↳ récupérer des données existantes

### Exemple

```php
<?php
// n'oubliez pas de faire votre connexion à la base de données ici, avant les commandes ci-dessous

$sql = "SELECT * FROM utilisateurs";

foreach ($pdo->query($sql) as $row) {
    echo "Nom : " . $row['nom'] . " - Email : " . $row['email'] . "<br>";
}
?>
```

## UPDATE (mettre à jour)

↳ modifier une donnée déjà existante dans la base

### Exemple

```php
<?php
// n'oubliez pas de faire votre connexion à la base de données ici, avant les commandes ci-dessous

$sql = "UPDATE utilisateurs SET email = :email WHERE id = :id";

$stmt = $pdo->prepare($sql);

$stmt->execute([
    ':email' => 'flo.perso@example.mail',
    ':id' => 1,
]);

echo "Utilisateur mis à jour avec succès !";
?>
```

## DELETE (supprimer)

↳ retirer une donnée existante

### Exemple

```php
<?php
// n'oubliez pas de faire votre connexion à la base de données ici, avant les commandes ci-dessous

$sql = "DELETE FROM utilisateurs WHERE id = :id";

$stmt = $pdo->prepare($sql);

$stmt->execute([':id' => 1]);

echo "Utilisateur supprimé avec succès !";
?>
```
