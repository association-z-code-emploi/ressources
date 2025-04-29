---
tags:
  - tutorials
  - a11y
---

# ARIA et la sémantique HTML

> ℹ️ Ce cours demande des connaissances basiques en HTML, mais aussi très bientôt en JavaScript.

## Sémantique HTML

On parle de **sémantique HTML** quand on fait référence à l'utilisation d'éléments HTML qui ont une **signification particulière**, comme `<header>` pour un en-tête, `<nav>` pour un menu de navigation, ou même simplement `<h1>` pour un titre. Cette sémantique aide les technologies d'assistance à **comprendre la structure du contenu de la page**, et donc de permettre une meilleure navigation.

L'utilisation des bons éléments HTML permet de :

1. **structurer correctement** la page pour les utilisateurs de technologies d'assistance
2. rendre le contenu **plus compréhensible et navigable**, notamment pour les personnes en situation de handicap

### Exemples d'élément HTML importants pour l'accessibilité

- **les titres** : correctement utilisés, les balises `<h1>`, `<h2>`, etc... permettent de **définir les titres**, donc les lecteurs d'écran ont besoin pour permettre aux utilisateurs de **navigueur rapidement**.
- **les listes** : `<ul>`, `<ol>` et `<li>` permettent de **regrouper des éléments similaires**, et donc d'indiquer qu'ils sont "ensembles".
- **les formulaires** : des balises comme `<label>` associent un texte à un champ de formulaire, ce qui **améliore l'expérience utilisateur** lors du remplissage d'un formulaire.
- et d'autres !

### Exemples d'utilisations

**Mauvaise utilisation** :

```html
<div>
  <p>Collecte de fonds</p>
</div>
```

↳ est-ce un titre ? une description ? une indication pour effectuer une action ?
↳ `<div>` est une balise "joker" qui ne sert qu'à rassembler visuellement des éléments, donc aucun contexte ajouté ici à nos questions d'avant

**Bonne utilisation** :

```html
<header>
  <h1>Collecte de fonds</h1>
</header>
<main>
  <p>Aidez-nous à réunir la somme nécessaire à ...</p>
</main>
<footer>Tous droits réservés - Association ...</footer>
```

↳ chaque partie de la page est séparée des autres (`<header>`, `<main>` et `<footer>`)
↳ on saura retrouver le titre grâce à `<h1>`, le paragraphe descriptif avec `<p>` et les mentions légales dans le `<footer>`

## ARIA (Accessible Rich Internet Applications)

Développez en 2008 par le **Web Accessibility Initiative** (_WAI_), **ARIA** est un ensemble d'**attributs** que l'on peut ajouter aux éléments HTML pour améliorer l'accessibilité lorsque la sémantique de ces éléments n'est pas suffisant. **ARIA ne change pas l'apparence visuelle d'un site**, mais aide les technologies d'assistance (comme les lecteurs d'écran) à mieux comprendre et interagir avec les contenus d'une page.

Les trois principaux éléments d'ARIA sont :

- définir la fonction d'un élément par un **rôle** (eg. un bouton, un lien, ...)
- donner des informations supplémentaires sur un élément par des **propriétés** (eg. un texte qui décrit un élément)
- décrire l'état actuel d'un élément par un **état** ou des **valeurs** (eg. un bouton qui est activé ou non)

### Attributs ARIA

#### `role`

Sert à définir la fonction d'un élément, surtout si ce n'est pas clair en HTML sémantique.

**Par exemple** :

```html
<div role="alert">Votre session va expirer dans 2 minutes</div>
```

↳ ici, même si la `div` n'attend aucune interaction, elle informe l'utilisateur

#### `aria-label`

Sert à donner un nom accessible à un élément sans afficher ce texte à l'écran ; comme décrire un bouton, une icône ou tout autre élément non-textuel pour les lecteurs d'écran.

**Par exemple** :

```html
<button aria-label="Fermer la fenêtre">
  <img src="close-icon.png" alt="" />
</button>
```

↳ même sans texte visible, l'utilisateur sait que c'est pour "fermer la fenêtre". On n'ajoute pas de détails dans le `alt` pour ne pas être redondant dans l'information qui a déjà été donné par `aria-label`.

#### `aria-hidden`

Sert à cacher un élément aux technologies d'assistance ; permet d'ignorer des éléments purement décoratifs ou redondants.

**Par exemple** :

```html
<p><span aria-hidden="true">ℹ️</span>Information importante</p>
```

↳ l'emoji "informations" est inutile pour l'accessibilité, d'autant qu'il serait sinon lu comme la lettre "i" dans ce cas précis

#### `aria-live`

Sert à annoncer automatiquement des changements dynamiques sur la page, pour informer les utilisateurs sans qu'ils aient besoin d'interagir.

**Par exemple** :

```html
<div aria-live="polite">Nouveau message reçu !</div>
```

↳ permettra au lecteur d'écran de lire "Nouveau message reçu !" dès que le contenu change

#### `aria-expanded` et `aria-controls`

Le premier indique si un élément est étendu ou replié ; utilisé pour les menus déroulants, accordéons, etc...
Le second fait comprendre que les liens entre un bouton et sa zone qu'il ouvre/modifie.

**Par exemple** :

```html
<button aria-expanded="false" aria-controls="menu1">Menu</button>
<div id="menu1">Contenu du menu</div>
```

↳ l'utilisateur saura que le bouton agit sur "menu1" et lorsqu'il ouvrira le menu, on pourra changer `aria-expanded="true"`

### Quand utiliser ARIA ?

1. **Ne pas utiliser ARIA ... sauf exception** : mal utilisé, ARIA crée plus d'erreurs et ne rend pas automatiquement un site plus accessible. Il vaut mieux plutôt utiliser les bonnes balises HTML sémantiques.
2. **Ne pas ajouter ARIA inutilement** : les éléments HTML fonctinnent déjà bien sans ajout d'ARIA et ajouter ARIA peut rendre le code plus compliqué et moins performant (voir point précédent).
3. **Toujours rendre les éléments accessibles au clavier** : tous les éléments interactifs doivent être accessibles sans la souris.
4. **Ne jamais cacher un élément focusable** : les outils d'assistance vont sinon l'ignorer.
5. Donner un nom accessible aux éléments interactifs : chaque élément interactif doit décrire clairement son action. Ce peut être un texte visible, un `alt` d'une image ou un `label` lié à un élément.

---

## Aller plus loin

- ["A11ycasts - Why headings and landmarks are so important"](https://www.youtube.com/watch?v=vAAzdi1xuUY&index=20&ab_channel=ChromeforDevelopers) 🎞️🇬🇧 (sous-titres officiels en anglais)
- ["TinkUK - How screen readers navigate data tables"](https://tink.uk/how-screen-readers-navigate-data-tables/) 📖🇬🇧
- ["NVAccess"](https://www.nvaccess.org/download/) ⚙️🇬🇧 : un lecteur d'écran populaire et gratuit, mais seulement pour Windows. Si vous êtes sous Mac, testez plutôt la fonctionnalité native de VoiceOver. Si vous utilisez Linux, testez alors Orca.
- ["ARIA Landmarks Example"](https://www.w3.org/WAI/ARIA/apg/patterns/landmarks/examples/HTML5.html) ⚙️🇬🇧 : liste tous les éléments HTML natifs qui définissent des zones de repère ainsi que leur rôle sur une page web.

---

## Exercices

Les exercices [02_ARIA_et_HTML](https://github.com/association-z-code-emploi/exercices-a11y/tree/main/02_ARIA_et_HTML) sont recommandés pour tester les connaissances sur les notions vues durant ce cours.
