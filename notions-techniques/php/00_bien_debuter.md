---
tags:
  - tutorials
  - php
---

<img src="https://www.php.net/images/logos/php-logo-white.svg" alt="PHP official banner" width=200>

# Bien débuter

---

## Introduction

### Qu'est-ce que PHP ?

- _PHP Hypertext Preprocessor_
- spécialement conçu pour générer des pages web (mais aussi à d'autres choses)
- langage de script opensource
- langage interprété donc besoin d'un serveur HTTP :
  - le fichier PHP a des instructions
  - l'interpréteur a un rôle de "traducteur" et enverra la trad. au navigateur
  - le navigateur ne sait lire que le résultat donné par l'interpréteur

---

## Installation

Pour créer des applications en PHP, il faut d'abord installer PHP sur son ordinateur. Il peut être installé sur Windows, macOS ou différentes versions de Linux et il existe plusieurs façons de procéder :

- sur le [site officiel de PHP](https://www.php.net/manual/fr/install.php)
- en utilisant des outils comme APT (sur Linux) ou Homebrew (sur macOS)
- en utilisant des outils en ligne comme :
  - [OneCompiler](https://onecompiler.com/php)
  - [PHP Sandbox](https://onlinephp.io/)

Une fois l'installation terminée, vous pouvez tester si tout fonctionne en lançant un petit script PHP. Par exemple :

```php
<?php echo 'Hello, World!'; ?>
```

Ce code doit afficher "Hello, World!" dans votre navigateur si PHP est bien installé !

<img src="https://media1.tenor.com/m/X60UMvwiQSUAAAAd/thumbs-up.gif" height=300 alt="Chow Yun-Fat thumbs up gif">

---

## Feuille de route

Ci-dessous se trouve une **feuille de route** ("_roadmap_") : une liste des notions techniques, classées dans un ordre logique de progression.

Le but n’est pas de tout faire, ni de tout maîtriser d’un coup, mais d’avoir une feuille de route pour savoir vers quoi progresser. Considérez que les sujets "Gestion de fichiers" et "Formulaires" sont de vrais bonus, complètement optionnels pour démarrer votre formation !

Allez-y étape par étape, en vous arrêtant sur les différents sujets et ceux que vous voulez explorer. Si un point bloque, ce n’est pas grave : ça viendra avec le temps et la pratique.

1. Éditeur de code et installation
2. Syntaxe PHP basique :

- variables et portées
- types de données et "jonglage" ("_casting_") de type
- sortie ("_output_") et débugage (`echo`, `print`, `print_r`, etc...)
- constantes

3. Tableaux ("_arrays_")

- indexés
- associés
- imbriqués ("_nested_")

4. Conditions

- `if/else`
- `switch`

5. Boucles ("_loops_")

- `for`
- `while`

6. Fonctions

- Déclaration
- Paramètres
- `return`

7. Gestion de fichiers

- Lire
- Écrire

8. Formulaires

---

## Ressources en ligne

Voici une sélection de **ressources en ligne** : cours écrits, vidéos, tutos, exercices... Elles couvrent toutes plus ou moins les mêmes notions, mais le style change d’une plateforme à l’autre. L’idée, c’est de tester et que vous trouviez ce qui vous parle le plus, de faire le tri et à choisir un format adapté à votre manière d’apprendre.

Inutile de tout suivre de A à Z : choisis une ressource ou deux et avance avec celles-là !

- [PHP Tutorial](https://www.phptutorial.net/)
- [Learn PHP](https://www.learn-php.org/)
- [Tutorials Point](https://www.tutorialspoint.com/php/index.htm)
- [Grafikart](https://grafikart.fr/tutoriels/php)
- [Openclassroom - PHP](https://openclassrooms.com/fr/courses/918836-concevez-votre-site-web-avec-php-et-mysql)
- et toutes celles que vous pourriez découvrir !

Enfin, armez-vous de la [documentation officielle](https://www.php.net/manual/fr/) : la principale source de vérité concernant PHP !

---

## Mini-projets

C’est bien de lire ou regarder des tutos, mais le plus important, c’est de **faire par soi-même** !
Vous trouvez une [liste de mini-projets dans ce fichier](https://github.com/association-z-code-emploi/ressources/tree/main/idees-de-projets/php.md) : courts, simples à comprendre, mais faits pour apprendre à réfléchir, chercher, tester, corriger. C’est là que l'on construit vraiment des compétences.

Vous pourriez vous aider d’un tuto ou même d’une IA comme ChatGPT, mais c'est déconseillé lors de l'apprentissage car :

- ces outils peuvent se tromper ou donner des réponses inexactes (ce qu’on appelle des "hallucinations")
- ils donnent souvent des solutions toutes faites, donc vous apprenez moins qu’en vous posant la question ou en cherchant la solution vous-même

Même si c’est dur ou frustrant, faire l’effort de comprendre par soi-même, c’est ce qui fait toute la différence à long terme et vos formations y veilleront.

## Planning et movitation

On encouragera à se fixer un **planning simple** (par exemple 2h, 2 ou 3 fois par semaine). Ce n’est pas l’intensité qui compte, mais la **régularité**. Les bons réflexes viennent avec le temps, et les automatismes aussi.

Notez votre planning quelque part (papier, Calendar, Notion, etc...), et partagez-le avec quelqu'un de fiable, qui saura vous "surveiller" pour vous pousser à gagner en discipline !

**Mais surtout** : ne vous surchargez pas de travail, ne restez pas bloqué des heures sur un problème. Faîtes des pauses, faîtes autre chose entre vos temps de code. Votre planning sert aussi à cela !
