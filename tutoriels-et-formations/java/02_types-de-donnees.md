---
tags:
  - tutorials
  - java
---

# Les types de données ("_data types_")

Chaque variable va contenir une donnée, et cette donnée sera d'un type déterminé. Ces types peuvent être **primitifs** ou **non-primitifs**.

## Types de données _primitifs_

Une terminologie qui fait peur mais en fait il s'agit simplement de la forme la plus de ce qu'est une variable. En Java, les principaux types primitifs sont :

- `byte`
- `short`
- `int`
- `long`
- `float`
- `double`
- `boolean`
- `char`

> Les plus courants seront décrits ci-après.

## Types de données _non-primitifs_ (ou de _référence_)

Les différences entre les types primitifs et les non-primitifs :

- les primitifs sont prédéfinis et intégrés à Java, alors que les non-primitifs sont créés par le programmeur (sauf `String`)
- les non-primitifs peuvent être utilisés pour appeler des méthodes afin d'effectuer certaines opérations, alors que les primitifs ne le peuvent pas
- les primitifs doivent toujours contenir une valeur, tandis que les non-primitiufs peuvent être `null`

En Java, les principaux types primitifs sont :

- `String`
- `Array`
- `Classe`

> On détaillera ici seulement les Strings, alors que les Arrays et les Classes auront leurs propres cours dédiés.

## Détails des types de données

### Nombres

Les ordinateurs utilisent différentes façons pour traiter les nombres. En Java, différents types de nombres permettent de stocker un certain intervalle :

- **nombres entiers** (sans virgules) :
  - `byte` : entre -128 et 127
  - `short` : entre -32 768 et 32 767
  - `int` : environ 2 million en négatif et positif
  - `long` : un trèèèèès long intervalle

> ℹ️ **Pourquoi séparer ces intervalles plutôt que d'avoir "number" ?**
>
> Plus un intervalle est grand, plus cela demandera de "l'énergie" à la machine lors du calcul.
> Il est donc important dans les projets importants de bien choisir le type de nombre.
> **En tant que débutant**, on peut se contenter de `int`.

- **nombres flottants/décimaux** (avec virgules) :

- `float` : un très grand intervalle
- `double` : un _vraiment_ très grand intervalle

### Textes

On souhaitera souvent afficher du texte et, pour cela, on utilisera des caractères pour n'afficher qu'une seule lettre, ou des chaînes de caractères pour ... des chaînes de plusieurs caractères. Tous les symboles entre guillemets `" "` ou entre guillemets simples `' '` seront définis comme des chaînes de caractères.

- `char` : une simple lettre
- `String` : une chaîne ou un ensemble de lettres mis bout à bout

### Booléen

Un type binaire, qui peut être `true` (vrai) ou `false` (faux), rien entre les deux, rien d'autre.

C'est vraiment utile lorsqu'on veut stocker quelque chose qui peut être une option, par exemple.

### Null

` null` est particulier dans le sens où il n'est ni primitif, ni non-primitif. Il permet de représenter l'absence intentionnelle de valeur.

> ℹ️ Tout comme le nombre `0` est un nombre représentant une valeur vide en mathématiques, `null` est une valeur représentant la valeur vide des types en Java (et d'autres langages).

## Exemple des différents types de données :

```java
public class TypesDeDonnees {
    public static void main(String[] args) {
        int annee = 2025;
        double temperature = 12;
        boolean estFroid = true;
        String message = "Bienvenue à Lille !";

        System.out.println("Année : " + annee);
        System.out.println("Température : " + temperature + "°C");
        System.out.println("Fait-il froid ? " + estFroid);
        System.out.println(message);
    }
}
```

↳ **Output** :

```
Année : 2025
Température : 12°C
Fait-il froid ? true
Bienvenue à Lille !
```

> ℹ️ Dans le cours suivant, vous découvrirez comment combiner, faire des calculs ou comparer ces variables avec des [opérateurs](./03_operateurs.md) (texte, nombre, etc...).

---

## Exercices

Les exercices suivants sont recommandés pour ce cours-ci :

- [TBA](#) 🚧
