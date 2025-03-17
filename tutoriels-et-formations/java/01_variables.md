---
tags:
  - tutorials
  - java
---

# Les variables

En programmation, comme dans tout activité de résolution de problèmes, la partie la plus importante du travail est **de s'assurer que l'on a bien identifié le problème que l'on souhaite résoudre**. C'est une **GROSSE** erreur - mais malheureusement fréquente - de se lancer trop vite dans le code.

On devrait consacrer _tout le temps nécessaire_ à comprendre (ou à définir) l'**énoncé du problème**. Une bonne façon d'y parvenir est d'[expliquer à quelqu'un ce que nous cherchons à accomplir](https://fr.wikipedia.org/wiki/M%C3%A9thode_du_canard_en_plastique) ! 🦆

Une fois que l'on sait ce que l'on souhaite résoudre, il faut essayer de décomposer en petites opérations simples. On constatera que la plupart du temps, il existe déjà quelque chose (par exemple, une méthode ou un package Java) que l'on peut réutiliser. Cherchez sur Google ou dans encore mieux : dans la documentation !

Dans ce cours, on va découvrir 1 des 5 éléments fondatmentaux, qui permettra de réaliser des programmes simples: **les variables** !

On ne voit pas d'algorithmes seulement dans l'informatique, on les retrouve en fait partout, comme par exemple dans une recette :

- Préchauffez le four à 210°C
- Beurrez le plat
- Faîtes fondre le beurre
- ...

L'objectif ici est "Préparez un plat X" et la recette est l'une des nombreuses approches possibles pour en préparer. En informatique et plus particulièrement en programmation, on utilise des algorithmes pour résoudre des problèmes spécifiques, et les variables font partie des outils permettant de définir un algorithme.

Écrire **un programme** (ou **un algorithme**) consiste à écrire une combinaison d'expressions (par exemple _1 + 12_). Une expression a toujours un résultat (_13_ dans notre exemple).

## Définir une variable

Une variable est ce qui va contenir une donnée, un calcul, un programme entier, ... Pour la définir, on aura besoin de lui attribuer un type de donnée, un nom unique qui devrait être assez descriptif pour deviner son contenu et enfin sa valeur.

```java
String prenom = "Jim";
```

- `String` signifie qu'il s'agit d'une chaîne de caractères (ie. du texte)
- `prenom` est le nom uniquement que l'on donne à la variable
- `"Jim"` est la valeur de cette variable, et qui est bien un texte comme annoncé avec `String`

Pour ensuite retrouver cette donnée, on référencera son nom (comme un label ou une étiquette) :

```java
String prenom = "Jim";
System.out.println(prenom); // affichera "Jim" dans le terminal
```

⚠️ En Java, une variable :

- doit être précédé de son type de donnée
- doit commencer par une lettre (pas de chiffres en premier)
- peut contenir des lettres, chiffres et `_` (underscore)
- est sensible à la casse (`Nom` et `nom` sont différents)

> ℹ️ Dans le cours suivant, vous découvrirez les [différents types de données](./02_types-de-donnees.md) (texte, nombre, etc...).

---

## Exercices

Les exercices [01_variables](https://github.com/association-z-code-emploi/exercices-java/tree/main/01_variables) sont recommandés pour pratiquer les notions vues durant ce cours.
