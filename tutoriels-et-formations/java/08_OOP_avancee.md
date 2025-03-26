---
tags:
  - tutorials
  - java
---

# OOP avancée

## Héritage ("_Inheritance_")

L'**héritage** est un concept fondamental de la programmation orientée objet où une nouvelle classe (appelée **sous-classe**) acquiert des attributs et des méthodes d'une classe "mère" (appelée **superclasse** ou **classe de base**). Cela facilite la **réutilisation du code**, sa **maintenabilité** (on n'a besoin de faire une éventuelle modification qu'à un seul endroit) et permet d'**organiser les classes en une hiérarchie claire**.

Une **superclasse** peut donc être **étendue** par une **sous-classe**.

Prenons l'exemple d'un service de transport :

```
                   ┌──────────────────┐
                   │     Vehicule     │  → Superclasse
                   │ - immatriculation│
                   │ - proprietaire   │
                   │ + rouler()       │
                   └────────▲─────────┘
         ┌──────────────────┴───────────────────┐
         │                                      │
┌────────┴─────────┐                   ┌────────┴─────────┐
│     Voiture      │  → Sous-classe ←  │      Camion      │
│ - nombrePortes   │                   │ - capaciteMax    │
│ + ouvrirCoffre() │                   │ + chargerFret()  │
└──────────────────┘                   └──────────────────┘
```

**En détails** :

- `Vehicule` est une **superclasse** contenant les attributs et méthodes communs
- `Voiture` et `Camion` sont des **sous-classes** qui héritent de `Vehicule` et ajoutent leurs propres spécificités

### Implémentation

Définissons d'abord la superclasse `Vehicule` :

```java
public class Vehicule {
  protected String immatriculation;
  protected String proprietaire;

  public Vehicule(String immatriculation, String proprietaire) {
    this.immatriculation = immatriculation;
    this.proprietaire = proprietaire;
  }

  public void rouler() {
    System.out.println("Le véhicule roule.")
  }
}
```

Créons ensuite une sous-classe `Voiture` qui hérite de la superclasse `Vehicule` :

```java
public class Voiture extends Vehicule {
  private int nombrePortes;

  public Voiture(String immatriculation, String proprietaire, int nombrePortes) {
    super(immatriculation, proprietaire);
    this.nombrePortes = nombrePortes;

    public void ouvrirCoffre() {
      System.out.println("Le coffre est ouvert.")
    }
  }
}
```

Enfin, utilisons ces classes :

```java
public class Main {
  public static void main(String[] args) {
    Vehicule maVoiture = new Voiture("1-ABC-234", "Jim", 3);
    maVoiture.rouler();
    maVoiture.ouvrirCoffre();
  }
}
```

**En détails** :

- `Voiture` **hérite** de `Vehicule` avec `extends Vehicule`
- `super(immatriculation, proprietaire)` appelle le **constructeur de la superclasse**
- `Voiture` ajoute un **nouvel attribut** `nombrePortes` et une **nouvelle méthode** `ouvrirCoffre()`

> ⚠️ Attention néamoins à plusieurs **limites** de l'héritage :
>
> - si on modifie `Vehicule`, toutes ses sous-classes peuvent en être affectées
> - une classe ne peut hériter que d'une seule superclasse (mais on verra de quoi contourner ce problème)
> - si `Voiture` et `Camion` sont **totalement différentes**, mieux vaut ne pas les forcer à hériter de `Vehicule`, quitte à finalement être leurs propres superclasses

### L'opérateur `instanceof`

Pour vérifier si un objet est une instance d'une classe ou d'une de ses superclasses, on va pouvoir utiliser `instanceof` :

```java
Voiture v1 = new Voiture();
boolean estVoiture = voiture instanceof Voiture; // true
boolean estVehicule = voiture instanceof Vehicule; // true (si Voiture hérite de Vehicule)
```

### Redéfinir les méthodes (`@Override`)

Une sous-classe peut **modifier** une méthode héritée avec `@Override` :

```java
public class Voiture extends Vehicule {
  private int nombrePortes;

  public Voiture(String immatriculation, String proprietaire, int nombrePortes) {
    super(immatriculation, proprietaire);

    // reste du constructeur de cette sous-classe
  }

  @Override
  public void rouler() {
    System.out.println("La voiture roule.")
  }
}
```

**En détails** :

- auparavant, `Voiture` héritait de la méthode `rouler()` de la superclasse `Voiture`, mais `@Override` remplace cette méthode par une nouvelle, tout en gardant le même nom
- la version de `Voiture` est maintenant spécifique

> ℹ️ L'annontation de `@Override` peut paraître étrange, mais il faudra bien l'indiquer avant la méthode remplaçante pour qu'elle prenne effet.

---

## Héritage unique ("_Singular inheritance_") ou les interfaces

Contrairement à certains langages comme C++, Java **n'autorise qu'une seule superclasse par classe** ; notamment pour éviter les conflits de méthodes. Heureusement, les **interfaces** permettent d'implémenter plusieurs méthodes sans hériter d'une classe unique, grâce au mot clé `implement` lors de la définition de la classe !

Ajoutons une interface `Rechargeable` pour nos véhicules :

```java
public interface Rechargeable {
  void recharger();
}
```

Puis ajoutons-la dans `Voiture` :

```java
public class Voiture extends Vehicule implements Rechargeable {
  private int nombrePortes;

  public Voiture(String immatriculation, String proprietaire, int nombrePortes) {
    super(immatriculation, proprietaire);

    // reste du constructeur de cette sous-classe
  }

  @Override
  public void recharger() {
    System.out.println("Le véhicule se recharge...")
  }
}
```

Cela permettra d'ajouter la méthode `recharger()` à n'importe quelle classe, sans qu'elle ne soit rattaché à une superclasse.

---

## Abstractions

Une classe **abstraite** ne peut pas être instanciée et doit uniquement être étendue (ie. héritée). Elle peut avoir des méthodes concrètes, et les sous-classes doivent implémenter ces méthodes abstraites.

```java
abstract class Vehicule {
  abstract void demarrer(); // méthode à implémenter
}

class Voiture extends Vehicule {
  @Override
  void demarrer() {
    System.outprintln("La voiture démarre.");
  }
}
```

---

## Encapsulation

L'encapsulation est l'un des principes fondamentaux de la **Programmation Orientée Objet** (**_OOP_**), avec l'**héritage** (vu dans le prédécent cours), l'**abstraction** (aussi vu dans le précédent cours) et le **polymorphisme**.

La différence avec les trois autres principes mentionnés est que l'**encapsulation** permet de **protéger les données sensibles** en restreignant leur accès direct et en imposant des méthodes dédiées pour les modifier.

Par exemple, dans le domaine médical, la protection des données des patients est **essentielle**.

Définissons d'abord une classe `Patient` où certaines informations, comme le **nom** et le **numéro de sécurité sociale** seront protégées en utilisant des **attributs préviés** :

```java
public class Patient {
  private String nom;
  private String numeroSecuriteSociale;

  // Getter pour le nom
  public String getNom() {
    return nom;
  }

  // Setter pour le nom
  public String setNom(String nom) {
    this.nom = nom;
  }

  // Getter pour le numéro de sécurité sociale
  public String getNumSecuriteSociale() {
    return numeroSecuriteSociale;
  }

  // Setter pour le numéro de sécurité sociale (protégé)
  public void setNumSecuriteSociale(String numero) {
    if (numero.length() == 15) {
      this.numeroSecuriteSociale = numero;
    } else {
      System.out.println("Numéro de sécurité sociale invalide !");
    }
  }
}
```

**En détails** :

- on déclare les **attributs** comme `private` **interdit** l'accès direct
- en créant des **méthodes** `get` et `set`, on peut contrôler l'accès aux données
- on peut **valider** des entrées avant de les modifier (eg. d'abord vérifier la longueur du numéro de sécurité sociale)
- en utilisant `this`, on évite les confusions entre **variable de classes** et **paramètres**

Dans le programme princiapl, nous allons pouvoir créer un patient et manipuler ses informations via les **méthodes** `get` et `set`, en garantissant la **protection** des données :

```java
public class Main {
  public static void main(String[] args) {
    Patient patient1 = new Patient();

    // on modifie les données via les setters
    patient1.setNom("Jim Feddy");
    patient1.setNumSecuriteSociale("123456789012345");

    // on affiche les données via les getters
    System.out.println("Nom du patient : " + patient1.getNom();)
    System.out.println("Numéro de sécurité sociale : " + patient1.getNumSecuriteSociale();)

    // tentative de mise à jour avec un numéro incorrect ; car moins de 15 chiffres
    patient1.setNumeroSecuriteSociale("1234"); // ❌ message d'erreur
  }
}
```

---

## Exercices

Les exercices [08_OOP_avancee](https://github.com/association-z-code-emploi/exercices-java/tree/main/08_OOP_avancee) sont recommandés pour pratiquer les notions vues durant ce cours.
