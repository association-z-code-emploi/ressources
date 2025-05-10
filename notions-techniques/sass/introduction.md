---
tags:
  - tutorials
  - sass
---

# Introduction et Installation de Sass CSS

**Sass** (_Syntactically Awesome Stylesheets_) est un préprocesseur CSS qui permet d'écrire du CSS de manière plus efficace, plus maintenable (ie. à mettre à jour) et modulable.

Cela permet :

- la possibilité de découper les styles en plusieurs fichiers
- les variables et mixins permettent d’éviter les répétitions
- la syntaxe plus claire avec l’imbrication des règles CSS
- la génération automatique de CSS optimisé

> ℹ️ Sass or SCSS ?
>
> Pour des raisons historiques, Sass (le préprocesseur) fournit deux syntaxes différentes : Sass (pas tout en majuscules) et SCSS.
>
> Le choix de l’un ou l’autre dépend en grande partie de vous, car les deux sont strictement équivalents en termes de fonctionnalités. À ce stade, ce n’est qu’une question d’esthétique !

## Installation de Sass

1. Vérifier si Node.js est (déjà) installé

Sass fonctionnant avec Node.js, il faut d'abord vérifier si Node.js est installé.

Dans un terminal, entrez la commande suivante :

```sh
node -v
```

↳ si la version de Node.js s'affiche, tout est bon !

Si ce n'est pas le cas, téléchargez-le ici : [https://nodejs.org](https://nodejs.org)

2. Installer Sass avec npm

Une fois Node.js installé, installez Sass avec la commande suivante :

```sh
npm install sass
```

3. Vérifier l’installation

Comme pour vérifier si Node.js est bien installez, entrez la commande suivante pour vérifier l'installation de Sass :

```sh
sass -v
```

↳ si la version de Sass s'affiche, tout est bon !

## Compiler un fichier Sass

Sass doit être converti en CSS pour être utilisé par le navigateur.

La commande ci-dessous prend (par exemple) le fichier `styles.scss` et génère un `styles.css` compréhensible par les navigateurs :

```sh
sass styles.scss styles.css
```
