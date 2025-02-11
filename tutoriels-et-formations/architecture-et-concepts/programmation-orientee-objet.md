---
tags:
  - tutorials
  - advanced
---

# Programmation Orientée Objet (POO)

> ℹ️ Les exemples utilisés seront pour PHP

La **Programmation Orientée Objet** (_POO_) est une méthode de programmation basée sur la création et la manipulation d’[objets](https://www.php.net/manual/fr/language.oop5.php). Ces objets représentent des entités (comme "Personne", "Entreprise", "Commande", etc...), avec des **propriétés** (variable-valeurs au sein de l'objet) et des **méthodes** (fonctions).

La **POO** a plusieurs avantages :

- elle structure plus simplement le code
- elle permet de ne pas se répéter :
  - on va rendre la base du code "générique" pour pouvoir la réutiliser
  - on va donc pouvoir maintenir et corriger le code plus facilement

## Concepts clés

- **Classe :** modèle pour créer des objets (eg. une "Voiture")
- **Objet :** instance ("exemplaire") d’une classe (eg. "Toyota")
- **Attribut :** une variable dans une classe (eg. sa "marque", sa "couleur")
- **Méthode :** une fonction dans une classe (eg. elle peut "rouler" ou "klaxonner")
- **Constructeur :** une méthode spéciale pour créer des exemplaires (eg. "ma_voiture" ou "ta_voiture")
- **Héritage :** permet de créer une classe à partir d’une autre (eg. "ma_voiture_de_course")

```php
<?php
class Voiture {
    public $marque;
    public $couleur;

    public function __construct($marque, $couleur) {
        $this->marque = $marque;
        $this->couleur = $couleur;
    }

    public function rouler() {
        echo "La voiture $this->marque de couleur $this->couleur roule !\n";
    }
}

$maVoiture = new Voiture("Toyota", "rouge");
$maVoiture->rouler(); // > La voiture Toyota de couleur rouge roule !
?>
```

**↳ En détails** :

- `$this->propriété` : fait référence à une propriété de l’objet
- `__construct` initialise les valeurs des propriétés ; on parle de "constructeur"
- `rouler()` est une méthode appelée sur l'objet `$maVoiture`

### Héritage des classes

Une classe peut "hériter" des propriétés et méthodes d’une autre classe, et en ajouter des nouvelles - de propriétés et méthodes.

```php
<?php
class Animal {
    public $nom;

    public function __construct($nom) {
        $this->nom = $nom;
    }

    public function manger() {
        echo "$this->nom mange.\n";
    }
}

class Chien extends Animal {
    public function aboyer() {
        echo "$this->nom aboie : Woof !\n";
    }
}

$monChien = new Chien("Rex");
$monChien->manger(); // Rex mange.
$monChien->aboyer(); // Rex aboie : Woof !
?>
```

**↳ En détails** :

- `class Animal` : une classe avec seulement la méthode `manger()`
- `class Chien extends Animal` : une autre classe avec la méthode `aboyer()`, qui hérite des méthodes de `Animal` et de ses méthodes
- `new Chien("...")` aura donc les méthodes :
  - `manger()` (provenant de la classe `Animal`)
  - `aboyer()` (provenant de la classe `Chien`)

#### Polymorphisme

Similaire à l'héritage, le polymorphisme permet de modifier des méthodes des classes héritées pour leur donner un autre comportement que celui d'origine.

```php
<?php
class Animal {
    public function manger() {
        echo "$this->nom mange.\n";
    }
}

class Chat extends Animal {
    public function manger() {
        echo "$this->nom fait le difficile.\n";
    }
}

$animal = new Animal();
$animal->manger(); // Cet animal communique.

$monChat = new Chat();
$monChat->manger(); // Le chat miaule : Miaou !
?>
```

**↳ En détails** :

- `class Animal` : a la méthode `manger()` qui echo `$this->nom mange.\n`
- `class Chat` : hérite de la class `Animal`, mais va changer la méthode `manger()` qui existe déjà pour plutôt faire un echo `$this->nom fait le difficile.\n` à la place de `$this->nom mange.\n`
