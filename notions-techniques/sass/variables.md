---
tags:
  - tutorials
  - sass
---

# Les Variables en Sass

Comme dans les langages de programmation courants (Javascript, PHP, etc...), les variables en Sass permettent de stocker des valeurs réutilisables comme des couleurs, des tailles de police ou des espacements. Cela simplifie les éventuelles modifications du code et évite la répétition.

## Syntaxe

Comme en PHP, on utilise le symbole `$`, suivi par un nom (au choix), pour déclarer une nouvelle variable, puis pour l'appeler :

```scss
$primary-color: #6f6f6f; /* Ici, `$primary-color` est le nom de la variable */
$font-size: 16px;

body {
  color: $primary-color; /* En rappelant le nom de la variable, on peut réutiliser sa valeur - ici la couleur #6f6f6f - sans avoir besoin de réécrire "manuellement" cette couleur à chaque utilisation */
  font-size: $font-size;
}
```

## Les types de variables

Toujours comme dans les langages de programmation courants, Sass permet de stocker différents types de valeurs dans des variables :

| Type              | Description                                                                              | Exemple                                           |
| ----------------- | ---------------------------------------------------------------------------------------- | ------------------------------------------------- |
| **Nombres**       | une valeur numérique, comme une dimension, une durée, etc...                             | `$width: 100px;`                                  |
| **Chaînes**       | du texte, comme le nom d'une police d'écriture                                           | `$font: "Arial", sans-serif;`                     |
| **Couleurs**      | n'importe quel format pour une couleur (mot-clé, hexcode, rgb, etc...)                   | `$main-color: #6f6f6f;`                           |
| **Booleans**      | "vrai" ou "faux"                                                                         | `$is-colorblind-mode: true;`                      |
| **Listes**        | un ensemble de valeurs, utilisé toujours ensemble                                        | `$margins: 10px 20px 30px;`                       |
| **Maps (objets)** | un autre ensemble de valeurs, mais permettant d'en sélectionner ensuite une ou plusieurs | `$theme: (primary: #3498db, secondary: #2ecc71);` |

**Un exemple d’utilisation** :

```scss
$border-radius: 10px;
$spacing: (
  small: 5px,
  medium: 10px,
  large: 15px,
);

.button {
  border-radius: $border-radius;
  padding: map-get($spacing, medium);
}
```

## Le _scope_ des variables

En Sass, une variable peut être :

- **locale** : une variable déclarée à l’intérieur d’un sélecteur ou d’un bloc `{}` n’est accessible que dans ce bloc

```scss
.container {
  $padding: 20px;
  padding: $padding; // OK
}

.other {
  padding: $padding; // erreur : $padding n’existe pas dans cette régle CSS !
}
```

- **globale** : une variable définie à l’intérieur d’un bloc mais qui doit être accessible partout, utilise `!global`

```scss
.container {
  $primary: red !global;
}

h1 {
  color: $primary; // fonctionne grâce à !global
}
```

## Conseils et bonnes pratiques

- on déclare les variables globales en début de fichier
- on stocke toutes les variables dans un fichier propre, souvent nommé `_variables.scss`
- on évite d’utiliser `!global` sauf si nécessaire
- on utilise des `maps` pour organiser les variables complexes.

---

## Exercices

Les exercices suivants sont recommandés pour ce cours-ci :

- [01_bien-demarrer](/exercices-sass/01_bien-demarrer/README.md)
- [02_variables](/exercices-sass/02_variables/README.md)
- [03_listes](/exercices-sass/03_listes/README.md)
- [04_maps](/exercices-sass/04_maps/README.md)
- [05_local-global](/exercices-sass/05_local-global/README.md)
- [06_mini-projet-1](/exercices-sass/06_mini-projet-1/README.md)
