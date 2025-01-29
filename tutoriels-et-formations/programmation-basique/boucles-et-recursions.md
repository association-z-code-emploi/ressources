---
tags:
  - ressources
  - tutorials
  - basic
---

# Boucles et récursions

> Les exemples utilisés sont en PHP.

## Qu'est-ce qu'une boucle en algorithme ?

- Une boucle permet de répéter une série d'instructions plusieurs fois.
- On utilise une boucle quand on connaît le nombre d'itérations (répétitions) ou quand une condition doit être vérifiée.

### Types de boucles en PHP

- `for` : quand on connaît le nombre exact de répétitions
- `while` : quand on répète tant qu'une condition est vraie
- `foreach` : spécifique pour parcourir des tableaux (_arrays_)

### Exemple

```php
// Pour afficher les nombres de 1 à 5 avec une boucle for
for ($i = 1; $i <= 5; $i++) {
  echo $i . "\n"; // Affichera : 1 2 3 4 5
}
```

## Qu'est-ce que la récursivité ?

- La récursivité est une technique où une fonction s'appelle elle-même.
- Elle décompose un problème complexe en sous-problèmes identiques mais plus simples.
- Il faut toujours un cas de base pour arrêter la récursion, sinon elle tourne indéfiniment.

### Différences entre boucle et récursion

|                        | **Boucle**                                                                | **Récursion**                                                    |
| ---------------------- | ------------------------------------------------------------------------- | ---------------------------------------------------------------- |
| **Approche**           | Répète des instructions directement.                                      | Utilise une fonction qui s'appelle elle-même.                    |
| **Condition d'arrêt**  | Utilise un compteur (souvent appelé `i`) ou une condition dans la boucle. | A besoin d'une condition pour arrêter les appels de fonction.    |
| **Performance**        | En général plus rapide à exécuter.                                        | Plus élégante pour certains problèmes, mais consomme plus lente. |
| **Quand l'utiliser ?** | Pour des problèmes simples ou répétitifs (e.g., tableaux, calculs fixes). | Pour des problèmes où chaque étape dépend de la précédente.      |

### Pourquoi et quand utiliser la récursivité ?

- Quand une solution avec une boucle serait complexe ou peu lisible ; comme des boucles dans des boucles dans des boucles dans des boucles etc...

#### Exemples

- Parcourir un tableau imbriqué (_nested arrays_)
- Parcourir des dossiers et sous-dossiers
- Etc ...

```php
$data = [
    "Marvin",
    30,
    ["Lille", 59000]
];

function parcourirTableau($tableau) {
    foreach ($tableau as $valeur) {
        if (is_array($valeur)) { // Si c'est un sous-tableau
            parcourirTableau($valeur); // Appel récursif : on rappelle la fonction
        } else {
            echo "$valeur\n"; // Affiche la valeur
        }
    }
}

parcourirTableau($data);
// Affichera :
// Marvin
// 30
// Lille
// 59000
```

#### Exemple : récursion infinie (à éviter !)

```php
function boucleSansFin() {
    echo "Oups!\n";
    boucleSansFin(); // Aucune condition pour arrêter l'appel de la fonction
}

boucleSansFin(); // Affiche : Erreur !
```

#### Comparaison avec une boucle : calculer la somme des nombres de 1 à N

- Avec une boucle :

```php
function sommeAvecBoucle($n) {
    $somme = 0;
    for ($i = 1; $i <= $n; $i++) {
        $somme += $i;
    }
    return $somme;
}

echo sommeAvecBoucle(5); // Résultat : 15
```

- Avec une récursion :

```php
function sommeAvecRecursion($n) {
    if ($n === 0) { // Condition de sortie
        return 0;
    }
    return $n + sommeAvecRecursion($n - 1); // Appel récursif
}

echo sommeAvecRecursion(5); // Affichera : 15
```

---

#### Astuces

- Visualisez le problème : décomposez chaque étape comme une fonction indépendante
- Identifiez le cas de base : qu'est-ce qui mettra fin à la récursion ?
- Testez avec de petits exemples : utilisez des valeurs simples pour comprendre comment les appels se succèdent
- Ajoutez des `echo` pour voir chaque étape :

  ```php
  function exemple($n) {
      if ($n === 0) {
          return 0;
      }
      echo "Appel avec n = $n\n";
      return $n + exemple($n - 1);
  }

  exemple(3);
  // Affichera :
  // Appel avec n = 3
  // Appel avec n = 2
  // Appel avec n = 1
  ```
