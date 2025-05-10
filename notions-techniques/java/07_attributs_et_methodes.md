---
tags:
  - tutorials
  - java
---

# Attributs et Méthodes

Les **attributs** sont des **variables** qui contiennent des données sur un objet, définissant son état ou ses caractéristiques. Les **méthodes** sont des **fonctions** qui permettent d'effectuer des actions ou des opérations.

## Attributs/variables/champs/_fields_/...

Beaucoup de synonymes pour des précisions qui ne prennent de l'importance qu'à mesure que vous progresserez avec Java, donc ne prêtez pas attention à un mot ou l'autre pour le moment. Comprenez qu'il s'agit du même principe d'avec une variable.

La syntaxe générale d'un attribut est :

```
[modificateur_d_accès] [static] [final] type nom [= valeur_initiale];
          ↑                ↑       ↑      ↑   ↑           ↑
          1                2       3      4   5           6
```

1. définit qui peut **accéder** à l'attribut (facultatif)
2. un attribut `static` est **partagé** par toutes les instances de la classe (facultatif)
3. un attribut avec `final` ne peut **pas être modifié** après son initialisation (facultatif)
4. le type de données (`int`, `String`, `boolean`, ...)
5. le nom de l'attribut
6. une valeur de départ peut être attribuée (facultatif)

### Modificateurs d'accès

Ils définissent qui peut **accéder** à un attribut :

- `private` : seulement accessible dans la même classe
- (aucun modificateur) : accessible dans le **même groupe de classes**
- `protected` : accessible dans le **même groupe de classes** + par les **sous-classes**
- `public` : accessible **partout** dans l'application

Imaginons une classe `PocketMonster` avec les attributs suivants :

- `nom`
- `type`
- `niveau`

```java
public class PocketMonster {
  private String nom; // accès limité à la classe (PocketMonster)
  protected String type; // accès aux sous-classes
  public int niveau; // accessible partout, peut être lu/modifié directement
}
```

> ℹ️ Cela doit encore être confus, mais apprenez les bonnes pratiques :
>
> - `public` est parfois utilisé pour des classes contenant uniquement des données
> - on utilise souvent `private` pour protéger les attributs et y accéder via des **méthodes** particulières

### `static`, `non-static` et `final`

- `static` **appartient à la classe** (on peut y accéder directement via son nom) et non aux objets créés. Donc un seul exemple est partagé entre toutes les instances.
- `non-static` **appartient à chaque objet (instance)** de la classe. Chaque objet a donc sa propre copie avec des valeurs différentes !

En reprenant l'exemple précédent :

```java
public class PocketMonster {
  private String nom;
  protected type;
  public int niveau;

  static int totalCaptures = 0; // partagé par tous les objets

  public PocketMonster(String nom, String type, int niveau) {
    this.nom = nom;
    this.type = type;
    this.niveau = niveau;
    totalCaptures++; // augmente à chaque création d'une instance
  }
}
```

- `final` **ne peut pas être modifiée** après son affectation ; elle doit être initialisée ummédiatement ou dans le constructeur.
- `static final` est une **constante partagée par tous**. La convention veut qu'on la nomme en MAJUSCULES avec des tirets du bas ("`_`")

En reprenant l'exemple précédent :

```java
public class PocketMonster {
  private String nom;
  protected type;
  public int niveau;

  static int totalCaptures = 0;

  final int proprietaire; // doit être défini dès le départ et ne changement jamais
  static final int NUMERO_GENERATION = 1; // constante pour tous

  public PocketMonster(String nom, String type, int niveau) {
    this.nom = nom;
    this.type = type;
    this.niveau = niveau;
    this.proprietaire = proprietaire; // doit être défini au constructeur
    totalCaptures++; // augmente à chaque création d'une instance
  }
}
```

## Méthodes

Comme mentionné en introduction, une **méthode** permet d'exécuter des opérations sur des données (variables, attributs, etc...). Elles sont similaires aux **fonctions** dans d'autres langages comme JavaScript ou PHP.

Concrètement une méthode est un groupe d'instruction qui peut :

- prendre des **paramètres** (des valeurs en entrée)
- effectuer des **opérations**
- **retourner ou non un résultat**

### Définir une méthode

Une méthode doit **_toujours_** être définie dans une classe :

```java
public class PocketMonster {
  public void afficherNom(String nom) {
//  ↑     ↑        ↑           ↑
//  1     2        3           4
    System.out.println(nom); // affiche le nom donné en paramètre
  }
}
```

1. `public` indique que cette méthode est accessible depuis d'autres classes
2. `void` signifie que cette méthode ne **retourne** aucune valeur ; elle se contente de "faire quelque chose" sans donner suite
3. `afficherNom()` est simplement le nom de la méthode
4. `String nom` est le paramètre attendu par la méthode ; on précise le type de donnée et un nom temporaire qui n'existera que durant l'exécution de la méthode

### Appeler une méthode

Pour éxecuter la précédente méthode, on doit :

1. **créer un objet** (une **instance**) de la classe
2. **appeler la méthode** sur cet objet

```java
PocketMonster monster1 = new PocketMonster();
monster1.afficherNom("Jim");
// Output : "Jim"
```

### Avec plusieurs paramètres

Une méthode peut prendre **plusieurs paramètres**, séparés par des virgules (`,`) :

```java
public void afficherInfos(String nom, String type) {
  System.out.println("Nom : " + nom);
  System.out.println("Type : " + type);
}

PocketMonster monster1 = new PocketMonster();
monster1.afficherInfos("Jim", "Froid");
/* Output :
"Nom : Jim"
"Type : Froid"
*/
```

### Retourner une valeur

Une méthode peut **retourner** une valeur afin de la stocker dans une variable, pour l'afficher, la manipuler, etc...

```java
public int calculerNiveauSuivant(int niveauActuel) {
  return niveauActuel + 1;
}

int prochainNiveau = monster1.calculerNiveauSuivant(5);
System.out.println(prochainNiveau);
// Output : 6
```

Il est tout à fait possible d'avoir plusieurs `return` dans une même méthode, mais une seule sera exécutée :

```java
int niveauMaximal = 100;

public int calculerNiveauSuivant(int niveauActuel) {
  if(niveauActuel == niveauMaximal){
    return niveauActuel;
  }

  return niveauActuel + 1;

  return 0; // 👈 ne se déclenchera jamais, car il y a au moins l'un des deux return précédents qui passeront avec ce dernier
}
```

> ℹ️ Vous comprenez peut-être maintenant pourquoi on utilise parfois `void` comme type de retour : afficher dans le terminal ne fait rien de plus avec la valeur que l'afficher, on ne retourne donc "rien", donc `void`.

### Paramètres `final`

Il est possible de rendre un paramètre d'une méthode **final**, qui ne pourra pas être modifié :

```java
public int calculerNiveauSuivant(final int niveauActuel) {
  return niveauActuel + 1;
}

int prochainNiveau = monster1.calculerNiveauSuivant(5);
System.out.println(prochainNiveau);
// Output : ❌ erreur car on ne peut pas modifier 'niveauActuel' !
```

Il vaudra mieux attribuer la nouvelle valeur (le niveau suivant) dans une autre variable, variable dont on n'aura besoin que de façon temporaire. On utilisera alors une **variable locale**.

### Variable locale et portée

Une variable locale fonctionne comme une variable classique, mais elle ne peut être utilisée que dans la méthode où elle est déclarée :

```java
public int calculerNiveauSuivant(final int niveauActuel) {
  int resultat = niveauActuel + 1;
  return resultat;
}

int prochainNiveau = monster1.calculerNiveauSuivant(5);
System.out.println(prochainNiveau);
// Output : 6
System.out.println(resultat);
// Output : ❌ erreur, car la variable 'resultat' n'existe que durant l'exécution de la méthode !
```

Une variable locale **ne peut pas être utilisée en dehors de la méthode où elle a été créée**. **Chaque méthode a ses propres variables locales** et **elles ne sont pas partagées** entre méthodes.

> ℹ️ On retrouve aussi ce principe de **portée** ("**_scope_**") dans une **condition** ou une **boucle** : une variable créée durant l'un des ces deux éléments n'existera plus une fois l'instruction passée (soit l'une des réponses à la condition, soit un tour de boucle).

---

## Exercices

Les exercices [07_attributs_et_methodes](https://github.com/association-z-code-emploi/exercices-java/tree/main/07_attributs_et_methodes) sont recommandés pour pratiquer les notions vues durant ce cours.
