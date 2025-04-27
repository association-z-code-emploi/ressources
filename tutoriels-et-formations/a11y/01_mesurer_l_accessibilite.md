---
tags:
  - tutorials
  - a11y
---

# Mesurer l'accessibilité numérique

Pour savoir si un site est vraiment accessible, on utilise le **standard de référence** est le **WCAG** ("_Web Content Accessibility Guidelines_"). Il a été créé pour donner un **langage commun** sur l'accessibilité web, utilisé par de nombreux pays et entreprises.

> ⚠️ Les WCAG sont **des conseils**, pas des règles rigides. L'objectif est d'aider à rendre les sites **plus accessibles**, pas parfaits.

## Niveau de conformités WCAG

Il existe **3 niveaux** d'accessibilité :

- **niveau A** : support minimal (essentiel)
- **niveau AA** : support idéal (recommandé pour la plupart des sites)
- **niveau AAA** : support très avancé (rare pour tout un site)

À chaque niveau, il y a des critères à respecter. Par exemple, 30 critères pour A, 50 pour A+AA, 78 pour A+AA+AAA dans la version 2.2 des WCAG.

## Principes fondamentaux : le POUR

Pour mieux comprendre l'accessibilité, on peut retenir l'acronyme "**_POUR_**" :

- **P**ercevable
- **O**pérable
- **U**niversellement compréhensible (_Understandable_ en anglais d'origine)
- **R**obuste

### 1. Percevable

Les utilisateurs doivent pouvoir **voir**, **entendre** ou **renssentir** l'information, comme par exemple :

- ajouter un **texte alternatif** pour décrire une image importante
- mettre des **sous-titres** sur les vidéos
- ne pas utiliser uniquement la **couleur** pour transmettre un message, comme utiliser des icônes ou du texte

### 2. Opérable

Les utilisateurs doivent pouvoir naviguer et interagir sans problème, c'est à dire :

- avoir un site **utilisable au clavier** (sans souris)
- avoir un **menu déroulant** qui doit pouvoir s'ouvrir au clavier, pas seulement à la souris
- permettre d'**étendre le temps** pour remplir un formulaire

### 3. Compréhensible

Le site doit être **facile à comprendre** :

- en utilisant un **langage simple**
- en ayant une **navigation cohérente** entre les pages
- en affichant **clairement** les éventuels messages d'erreurs, en expliquant par exemple que "Le mot de passe est trop court" plutôt que "Erreur 113"

### 4. Robuste

Le site doit **fonctionner avec différents outils**, comme avec un lecteur d'écran, dans un navigateur, sur mobile, etc... même quand ces outils évoluent. De bonnes solutions sont :

- tester la navigation **uniquement au clavier**, dont les **claviers spéciaux**
- vérifier que le site fonctionne sur **différents appareils** (smartphones, tablettes, ordinateurs, ...)

## Tester l'accessibilité

Différentes méthodes permettent de concrètement tester l'accessibilité d'une page web :

- faire un **audit d'accessibilité** : un test pour vérifier où en est le produit par rapport aux standards, et qui peut se faire plusieurs fois **pendant tout le projet**, pas seulement au début
- utiliser des **outils automatiques**, comme des tests manuels ou avec des **technologies d'assistance** (lecteur d'écran, claviers spéciaux, ...)
- prendre en considération les **retours des utilisateurs**, en situation de handicap ou non

Le but n'est pas de chercher à rendre un site **100% accessible** tout de suite (c'est impossible !), mais faire que chaque **petite amélioration compte**. Ajouter un texte alternatif ou corriger un contraste peut faire une **grande différence** pour les utilisateurs qui sont bien réels.

---

## Aller plus loin

- ["Règles pour l’accessibilité des contenus Web (WCAG) 2"](https://www.w3.org/WAI/standards-guidelines/wcag/fr) 📖🇫🇷
- ["The A11Y Project"](https://www.a11yproject.com/) 📖🇫🇷 : un projet open source qui aide à rendre le contenu web accessible avec des checklists, des conseils et des outils basés sur les normes WCAG
- ["https://webaim.org/standards/wcag/checklist"](https://www.w3.org/WAI/standards-guidelines/wcag/fr) ⚙️🇬🇧 : gardez cette ressource dans vos favoris, car l’utiliser comme liste de contrôle lorsque vous commencerez à activement prendre en main l’accessibilité sera très utile

---

## Exercices

Les exercices [01_mesurer_l_accessibilite](https://github.com/association-z-code-emploi/exercices-a11y/tree/main/01_mesurer_l_accessibilite) sont recommandés pour tester les connaissances sur les notions vues durant ce cours.
