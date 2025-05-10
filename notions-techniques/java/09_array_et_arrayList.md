---
tags:
  - tutorials
  - java
---

# Array et ArrayList

Un **tableau** ("*array*") est une collection de variables du même type. C'est une structure de données essentielle qui permet d'organiser et de manipuler des ensembles de valeurs.

## Array

### Syntaxe et utilisation

Un tableau est donc déclaré comme une variable ordinaire, mais avec des crochets (`[]`) après le type :
```java
String[] mesTextes; // tableau de strings
int[] mesNombres; // tableau de int
...
public void maMethode(double[] tableauDeDoubles) { ... }
...
```

Déclarer un tableau ne créé pas encore le tableau ! Il faut l'**instancier** avec `new` :
```java
String[] plats = new String[5]; // crée un tableau avec 5 emplacements
plats[0] = "Salade";
plats[1] = "Frites";
plats[2] = "Pâtes";
plats[3] = "Steak";
plats[4] = "Pizza";
```

> ℹ️ Les emplacements dans un tableau se nomment des **indices** ; ils commencent toujours à 0.

Si on connaît déjà les valeurs, on peut utiliser un **array littéral** avec des accolades (`{}`) :
```java
double[] prix = {
  "2.50",
  "3.00",
  "1.50",
  "4.00",
  "3.50",
};
```

Pour **accéder** à un élément, on indique l'**indice** :
```java
System.out.println("En entrée: " + plats[0] + " pour " + prix[0] + "€"); // "En entrée: Salade pour 2.50€"
System.out.println("En principal: " + plats[1] + " ou " + plats[3] + " pour " + prix[3] + "€"); // "En plat principal: Frites ou Steak pour 4.00€"
```

> ℹ️ Accéder à un indice qui n'existe pas va générer une erreur. Avec les exemples ci-dessus, inutile de mettre un indice supérieur à 4 car il n'y a pas de valeurs en 5ème position (`plats[5]` → ❌)

On peut aussi **modifier la valeur** d'un élément :
```java
plats[3] = "Steak végétarien"; // remplace "Steak"
```

### Cas pratiques d'utilisation

#### Connaître la longueur d'un tableau

Vous découvrirez bientôt qu'il est très utile de connaître **la longueur d'un tableau**, et une méthode existe dans la classe `Array` pour ça :
```java
System.out.println("Nombre de plats dans le plats: " + plats.length); // "Nombre de plats dans le plats: 5"
```

> ℹ️ On ne mettra pas de parenthèses (`()`) après le nom de la méthode `.length` car il s'agit d'une **propriété** de la classe `Array`.

#### Parcourir un tableau

Il n'est pas pratique de devoir indiquer "à la main" chaque indice d'un tableau. Une manière de le faire plus simplement est d'utiliser `.length` pour connaître la **longueur maximale** du tableau, puis d'utiliser une **boucle** sur chacun de ses éléments :
```java
for(int i = 0; i < plats.length, i++) {
  System.out.println(plats[i]):
};
/*
Salade
Frites
Pâtes
Steak végétarien
Pizza
*/
```

#### Tableau à deux dimensions ("*nested arrays*")

Un tableau peut contenir des String, des nombres, des booléens, ... ou d'autres **tableaux** !

Combinons nos tableaux `plats` et `prix` :
```java
String[][] menu {
  { "Salade", "2.50" },
  { "Frites" ,"3.00" },
  { "Pâtes" ,"1.50" },
  { "Steak végétarien" ,"4.00" },
  { "Pizza" ,"3.50" },
};

for(int i = 0; i < menu.length, i++) {
  System.out.println(menu[i][0] + " - " + menu[i][1] + "€"):
};
/*
Salade - 2.50€
Frites - 3.00€
...
*/
```

**En détails** :
On peut lire/traduire un tableau de tableau ainsi : `nom du tableau[indice des emplacements du premier tableau][indice du second tableau du premier tableau]`.

Par exemple :
- avec `menu[0][0]` :
  - le premier `[0]` correspond au premier indice de `menu` → donc `{ "Salade", "2.50" }`
  - le second `[0]` correspond aussi au premier indice, mais du tableau `{ "Salade", "2.50" }` → donc `"Salade"`
- avec `menu[3][1]` :
  - `[3]` correspond au quatrième indice de `menu` → donc `{ "Steak végétarien" ,"4.00" }`
  - `[1]` correspond aussi au deuxième indice, mais du tableau `{ "Steak végétarien" ,"4.00" }` → donc `"4.00"`

> ℹ️ Encore une fois, souvenez-vous que les indices d'un tableau commencent à `0`. Donc dire "au premier indice" → `[0]`.

#### Ajouter un élément dans un tableau

En Java, **on ne peut redimensionner** un tableau. Il faudra alors créer un nouvel **array**, lui donner les valeurs de "l'ancien" tableau et ajouter les nouvelles.

```java
String[][] menu = {
    { "Salade", "2.50" },
    { "Frites", "3.00" },
    { "Pâtes", "1.50" },
    { "Steak végétarien", "4.00" },
    { "Pizza", "3.50" }
};

String[][] newMenu = new String[6][2];

for (int i = 0; i < newMenu.length; i++) {
    if (i < menu.length) {
        newMenu[i] = menu[i];
    } else {
        newMenu[i] = new String[] { "Poisson", "2.75" };
    }
    System.out.println(newMenu[i][0] + " - " + newMenu[i][1] + "€");
}
/*
Salade - 2.50€
Frites - 3.00€
...
Pizza - 3.50€
Poisson - 2.75€
*/
```

## ArrayList

`ArrayList` est une **liste dynamique** qui permet de stocker des éléments de manière plus flexible qu'un tableau (`Array`). Contrairement à un tableau fixe, une `ArrayList` peut **changer de taille** en fonction des ajouts et suppressions d'éléments.

De manière générale, `Array` et `ArrayList` marchent avec une logique similaire, mais s'utilisent différemment. Par exemple, on aura besoin d'importer le package `java.util.ArrayList` pour utiliser `ArrayList` :

```java
import java.util.ArrayList;

ArrayList<String> menu = new ArrayList<>(5); // pour une taille de 5 indices vides, mais sujette à modifications
// pour ajouter un élément, du premier indice vide (ici 0) vers le suivant, etc...
menu.add("Salade");
menu.add("Frites");
...
// on peut sinon ajouter à une position précise :
menu.add(4, "Pizza");
```

Pour accéder à un élément, on utilisera `.get(<index>)`. Pour le modifier, on utilisera `.set(<index>, <nouvelle valeur>)`. Mais "vraie" différence avec `Array` : on peut facilement supprimer une valeur avec `.remove(<index ou valeur>)`. On pourra aussi vérifier l'existance d'une valeur avec `.contains(<valeur>)` pour retourner un booléen, et connaître la longueur de la liste avec `.size()`.

```java
ArrayList<String> menu = new ArrayList<>(4);
menu.add("Salade");
menu.add("Frites");
menu.add("Pâtes");
menu.add("Steak végétarien");

System.out.println(menu.size()); // 4
System.out.println(menu.get(2)); // "Pâtes"
System.out.println(menu.set(2, "Tacos")); // on remplace la valeur par une nouvelle
System.out.println(menu.add(4, "Pizza")); // ajout de "Pizza" à l'indice 4
System.out.println(menu.contains("Pizza")); // true
...
```

## Array ou ArrayList ?

Comme c'est toujours un peu le cas avec la programmation : ça va dépendre du besoin, et il y a souvent la possibilité d'arriver à vos fins avec n'importe quel choix ; ce sera éventuellement plus difficile (comme pour agrandir ou réduire avec `Array`, car il faudra créer un nouvel `Array`).

Un `Array` a une taille **fixe**, ne peut donc pas ajouter ou supprimer un élément après création, mais cela peut-être une sécurité (eg. votre numéro de téléphone fera toujours la même longueur, même en le renouvellant).

Un `ArrayList` a une taille **dynamique**, peut être modifié via des méthodes et est pratique pour une liste qui peut changer (eg. votre nombre de téléphone, que ce soit 1, 2, 5 ou 10).

---

## Exercices

Les exercices [09_array_et_arrayList](https://github.com/association-z-code-emploi/exercices-java/tree/main/09_array_et_arrayList) sont recommandés pour pratiquer les notions vues durant ce cours.
