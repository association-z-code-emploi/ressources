---
tags:
  - tutorials
  - java
---

# Interface `Map`

Une `Map` permet de **lier une clé à une valeur**, comme associer un code-barre à un article ou à un livre.
Chaque **clé est unique** et permet de retrouver une **valeur associée**.

> ℹ️ Contrairement aux autres collections comme `List` (vu dans le précédent cours) ou `Set`, `Map` ne vient pas de l'interface `Collection`.

## Implémentation d'une `Map`

Il existe deux manières d'implémenter une `Map` :
- avec `HashMap`, qui est rapide mais **sans pouvoir garantir d'ordre**
- ou avec `TreeMap`, qui trie automatiquement les clés par **ordre alphabétique**

```java
Map<String, String> bibliotheque = new HashMap<>();
//                              ou new TreeMap<>()
```

↳ ici, on indique que les clés sont des String, et les valeurs aussi

## Ajouter des éléments

Pour ajouter des éléments à une `Map`, on utilise sa méthode `put()` :

```java
bibliotheque.put("Conte_001", "Le Petit Prince");
bibliotheque.put("Philo_013", "Le Monde de Sophie");
bibliotheque.put("SF_142", "Dune");
```

↳ ici, les clés sont des codes de livre pour et les valeurs sont les titres des livres

> ℹ️ Le format des clés n'a pas d'importance : mettez ce que vous désirez, tant que cela vous aide à retrouver la valeur (ici le livre) que vous cherchez !

## Accéder à un élément

Pour accéder à un des éléments d'une `Map`, on utilise sa méthode `get()` :

```java
String titre = bibliotheque.get("SF_142"); // "Dune"
```

↳ ici, on indique encore le nom de la `Map`, puis on entre la clé ("SF_142") pour obtenir sa valeur ("Dune")

### Obtenir une valeur par défaut

Si la clé demandée ne correspond à rien, on peut retrourner une valeur par défaut :

```java
String titre = bibliotheque.get("Cui_001", "Livre inconnu"); // "Livre inconnu"
```

## Parcourir une `Map`

Contrairement aux Array, on va devoir utiliser une autre méthode de `Map` pour itérer dessus :

```java
// Pour avoir accés aux clés et à leurs valeurs
for (String code : bibliotheque.keySet()) {
  System.out.println("Code : " + code + " , Titre : " + bibliotheque.get(code));
}

// Pour avoir accès aux valeurs uniquement
for (String titre : bibliotheque.values()) {
  System.out.println("Titre : " + titre);
}
```

---

## Exercices

Les exercices [10_interface_map](https://github.com/association-z-code-emploi/exercices-java/tree/main/10_interface_map) sont recommandés pour pratiquer les notions vues durant ce cours.
