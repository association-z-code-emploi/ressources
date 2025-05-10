---
tags:
  - tutorials
  - java
---

# Gestion des erreurs et exceptions

Une **exception** est une erreur qui se produit pendant l'exécution d'un programme. Les exceptions permettent de gérer proprement ces erreurs au lieu de laisser le programme planter brutalement ; on doit gérer cette situation avant de poursuivre.

Par exemple, lors d'une authentification, si un utilisateur entre un mot de passe vide, on peut déclencher une exception.

## Pile d'appels ("*Call stack*")

La **pile d'appels** représente l'ordre des méthodes appelées. Par exemple, si une méthode `verifierUtilisateur()` appelle `verifierMotDePasse()`, qui appelle `accederCompte()`, la pile d'appels ressemble à ceci :
```text
1. verifierUtilisateur
2. verifierMotDePasse
3. accederCompte
```

Mais si une erreur survient dans `accederCompte()`, l'exception remonte la pile jusqu'à ce qu'une méthode la capture :
```text
1. accederCompte
2. verifierMotDePasse
3. verifierUtilisateur
```

## Lancer une exception ("*Throwing exception*")

Si une erreur est détectée, une exception peut être déclenchée avec `throw` :

```java
public void verifierMotDePasse(String motDePasse) throws Exception {
  if(motDePasse.isEmpty()) {
    throw new Exception("Le mot de passe ne peut pas être vide.");
  }

  // Reste du code si le mot de passe n'est pas vide ...
}
```
↳ Dès que l'exception est lancée, le programme s'**arrête** immédiatement et cherche un moyen de gérer l'erreur reçue.

## Capture une exception ("*Catching exception*")

On peut gérer une exception avec `try-catch` :
```java
public void authentifier(String utilisateur, String motDePasse) {
  try {
    verifierMotDePasse(motDePasse);
    Systeme.out.println("Authentification réussie.");
  } catch (Exception e) {
    System.out.println("Erreur : " + e.getMEssage());
  }
  System.out.println("Tentative d'authentification termiéne.")
}
```
↳ Si `verifierMotDePasse()` déclenche une exception, le message d'erreur s'affichera dans le `catch`, puis le programme continuera ensuite.

> ℹ️ De manière générale, on ne se contentera pas d'afficher le message d'erreur dans le terminal mais plutôt de donner une réponse à l'utilisateur, comme lui indiquer que le mot de passe est incorrect, l'amener sur une page d'erreur, etc... Néanmoins, il est toujours bon pour un développeur d'afficher le message, afin d'avoir des informations sur la cause.

---

## Exercices

Les exercices [11_gestion_erreurs_et_exceptions](https://github.com/association-z-code-emploi/exercices-java/tree/main/11_gestion_erreurs_et_exceptions) sont recommandés pour pratiquer les notions vues durant ce cours.
