---
tags:
  - tutorials
  - java
---

# Classes et Objets

Java est donc un langage de programmation orienté objet : il a besoin de classes pour organiser le code en regroupant des **données** (ie. variables) et des **actions** (ie. méthodes) dans une seule unité logique.

Pour les petits programmes, une seule classe contenant la méthode `main()` peut suffire ; c'est ce que vous avez utilisé jusqu'à présent. Mais à mesure que l'application grandit, il devient compliqué de tout gérer dans une seule classe. Il va alors être préférable de **diviser le code en plusieurs classes** pour améliorer la structure et la lisibilité du programme.

> ℹ️ Rappelez-vous du principe **\*D**on't **R**epeat **Y**ourself\* avec les méthodes !

Chaque classe Java devrait être enregistréee dans son propre fichier, sachant qu'une application Java peut contenir **autant de classes que nécessaire**. De plus, Java propose de nombreuses **classes prédéfinies** (comme `Scanner`), évitant d'avoir à tout programmer soi-même.

Ce principe est nommé "OOP" pour "**\*O**bject **O**riented **P**rogrammation\*" (en français "POO" ; "Programmation Orientée Objet").

## Classe Java

### Base d'une classe

Elle est composée de plusieurs éléments essentiels, mais commençons d'abord par la base d'une classe, sans autres éléments :

```java
public class MaClasse {
  ...
}
```

Cela crée une classe publique nommée "MaClasse", sans variables ni méthodes.

> ℹ️ Chaque classe doit commencer par une majuscule, et doit être enregistrée dans un **fichier portant son nom**, suivi par l'extension`.java`.

### Avec des variables/_fields_

Une classe peut contenir des **variables** qui vont stocker des données :

```java
public class Voiture {
  String marque;
  String modele;
  String couleur;
}
```

Ici, la classe `Voiture` possède **trois variables** mais **aucune méthode**. Aucune valeur n'est associée à ces variables pour le moment ; différentes voitures ont différentes marques, modèles et couleurs !

### Avec un construteur

Il s'agit d'une méthode spéciale appelée lors de la création d'un objet pour l'initialiser :

```java
public class Voiture {
  String marque;
  String modele;
  String couleur;

  // Ici, le constructeur par défaut :
  public Voiture() {
    ...
  }

  // Ici, le constructeur avec des paramètres :
  public Voiture(String marqueVoiture, String modeleVoiture, String couleurVoiture) {
    this.marque = marqueVoiture;
    this.modele = modeleVoiture;
    this.couleur = couleurVoiture;
  }
}
```

Ici, le **constructeur par défaut** ne fait rien, alors que le **second constructeur** initialise les variables avec les valeurs qui lui sont fournies.

`this` permet de référencer une **variable d'objet**, lorsqu'on l'aura crée à partir de sa classe. Plus de détails sur ce mot-clé plus bas dans ce cours.

### Avec des méthodes

Une **méthode** permet d'exécuter des actions sur les champs d'une classe :

```java
public class Voiture {
  String marque;
  String modele;
  String couleur;

  // Ici, pour modifier la couleur :
  public void changerCouleur(String nouvelleCouleur) {
    this.couleur = nouvelleCouleur;
  }
}
```

Ici, la méthode `changerCouleur()` va pouvoir modifier le champ `couleur`, en lui donnant une valeur entre parenthèses (`(...)`) qui sera assigné à une variable temporaire (eg. `nouvelleCouleur`) pour en faire quelque chose durant la méthode (eg. changer la couleur).

> ℹ️ Les méthodes sont décrites plus en détail dans un prochain cours.

### Avec des classes imbriquées

Une **classe imbriquée** (ou **_nested class_**) est définie à l'intérieur d'une autre classe.

```java
public class MaClasse {
  public static class MaClasseImbriquee {
    ...
  }
}
```

Ici, la classe `MaClasseImbriquee` est **contenue** dans `MaClasse`. Elle peut-être utilisée uniquement dans le cadre de cette dernière.

### Avec tous ... ?

Toutes les classes Java ne continennent pas forcément tous ces éléments. Tout va dépendre de leur rôle dans l'application.

Certaines ne possèdent que des **variables** (pour stocker des données), d'autres ne contiennent que des **méthodes** (pour effectuer des opérations).

Voici cependant un exemple avec tous les éléments mentionnés jusqu'à présent :

```java
public class Voiture {
  String marque;
  String modele;
  String couleur;

  public void changerCouleur(String nouvelleCouleur) {
    this.couleur = nouvelleCouleur;
  }

  public Voiture(String marqueVoiture, String modeleVoiture, String couleurVoiture) {
    this.marque = marqueVoiture;
    this.modele = modeleVoiture;
    this.couleur = couleurVoiture;
  }
}
```

On ne peut toujours pas faire grand-chose avec ce type de code car on manque d'une façon de l'utiliser !

## Objets Java

Une classe est comme un **modèle** (ou un **plan**) pour créer des objets. Dans les précédents exemples, on a pu définir à quoi devrait ressembler toutes voitures. Un **objet** est un **exemplaire** de la classe, avec des éléments communs et d'autres personnalisables grâce à sa classe. On parle alors d'**instance** de classe.

### Création d'un objet

Ci-dessous, on crée **deux objets** (`voiture1` et `voiture2`), ou plutôt on "**instancie des objets**", ce qui signifie **créer des nouveaux objets** à partir du modèle fourni par la classe (ici `Voiture`).

```java
public class Voiture {
  String marque;
  String modele;
  String couleur;

  public void changerCouleur(String nouvelleCouleur) {
    this.couleur = nouvelleCouleur;
  }

  public Voiture(String marqueVoiture, String modeleVoiture, String couleurVoiture) {
    this.marque = marqueVoiture;
    this.modele = modeleVoiture;
    this.couleur = couleurVoiture;
  }

  public static void main(String[] args) {
    Voiture voiture1 = new Voiture("Toyota", "Corolla", "rouge");
    Voiture voiture2 = new Voiture("Lancia", "500", "jaune");


    System.out.println(voiture1.marque); // "Toyota"
    System.out.println(voiture2.couleur); // "jaune"

    voiture2.changerCouleur("blanche");
    System.out.println(voiture2.couleur); // "blanche"
  }
}
```

**En détails** :

- `voiture1` et `voiture2` sont des **instances de la classe** `Voiture`
- chaque instance possède ses **propres valeurs** de champs (eg le modèle de `voiture2` est `500`)
- on leur donne des valeurs de départ via les paramètres du **constructeur** (`new Voiture(...)`) pour directement associer certaines valeurs à l'objet ; plutôt que de devoir faire `voiture1.marque = Toyota; etc...` manuellement
- remarquez aussi le **type de donnée** `Voiture` en début de ligne

On peut ainsi accéder à leurs propriétés et méthodes grâce au nom de l'instance (eg. `voiture1`), suivi par un point (`.`) et du nom de la variable (eg. `.marque`) ou de la méthode (`.changerCouleur()`). C'est pour cette raison que l'on a besoin de `this.` : cela permet de référencer la variable d'une instance d'objet sans affecteur les autres.

---

Ce qui a été abordé dans ce cours ne couvre que les bases des classes en Java. Vous devrez également en apprendre plus sur l'utilisation des **champs** et les **méthodes**, mais aussi sur des notions plus avancées dans les prochains cours comme l'**héritage**, l'**encapsulation**, les **interfaces**, etc...

---

## Exercices

Les exercices [06_classes_et_objets](https://github.com/association-z-code-emploi/exercices-java/tree/main/06_classes_et_objets) sont recommandés pour pratiquer les notions vues durant ce cours.
