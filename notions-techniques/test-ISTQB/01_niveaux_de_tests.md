---
tags:
  - tutorials
  - test
  - istqb
---

# Les niveaux de tests

Le **test logiciel et d'application** contient différents **niveaux** de test, leur **but**, leurs **responsabilités**, et leurs **relations** entre-eux. Ces niveaux s'appliquent à toutes les méthodologies (classiques ou agiles).

## Test unitaire (Unit Testing)

Ils servent à vérifier le **fonctionnement isolé** d'une **plus petite unité de code** : une fonction, une méthode, un composant, etc... On écrit ces tests durant la **phase de développement**, souvent par les **développeurs** eux-même.

**Par exemple**, pour une fonction en JavaScript :

```js
function addition(a, b) {
  return a + b;
}
```

On testera si `addition(2, 3)` renvoie bien `5`.

Les **avantages** sont :

- une détection très précoce des bugs,
- donc un coût de correction minimal.

Les **limites** sont :

- de donner un faux sentiment de sécurité si fait isolément chaque élément,
- car on ne teste pas tout de suite les interactions entre modules.

## Test d'intégration

Ils servent à vérifier la **l'interaction entre plusieurs unités**. On s'assure que les modules interagissent entre-eux comme prévu. Les **développeurs** peuvent participer à ces tests, mais l'aide d'un **testeur** est déjà essentiel.

**Par exemple** :

- le module "panier" appelle correctement le module "paiement"
- la fonction `getUserData()` récupère bien les infos depuis la base de données
- ...

Les **avantages** sont :

- de détecter les erreurs d'interface entre modules,
- et de vérifier la cohérence du flux global ("*workflow*").

Les **limites** sont :

- des tests plus lents et plus complexes à écrire que le test unitaire
- de nécessiter parfois un environnement plus complet (base de données, APIs, ...)

## Test système (System Testing)

Ils servent à vérifier que le **système complet**, en tant que produit fini, **répond aux exigences fonctionnelles et non fonctionnelles**. Ce sont des tests rédigés par des **testeurs professionels** ("QA")

**Par exemple** :

- vérifier que la commande s'effectue bien du panier à la confirmation
- tester la performance, la sécurité, la compatibilité
- ...

Les **avantages** sont :

- de valider le produit complet dans un environnement représentatif,
- et d'évaluer la qualité globale.

Les **limites** sont :

- d'être plus lent et plus coûteux
- de localiser plus difficilement la cause d'un échec (car tout le système est impliqué)

## Test d'acceptation (Acceptance Testing)

Ils servent à vérifier que le système **répond aux besoins de l'utilisateur ou du client**. C'est la **validation finale avant mise en production** ! On implique cette fois-ci le **client** et les **utilisateurs finaux**, ou le **Product Owner** de l'équipe.

**Par exemple** :

- l'utilisateur peut créer un compte, ajouter un produit et payer sans erreur
- les critères d'acceptation définis en amont sont tous respectés
- ...

Les **avantages** sont :

- de donne la validation officielle pour la livraison,
- et de mesurer la satisfaction utilisateur.

Les **limites** sont :

- qu'ils sont très dépendant de la clarté des exigences
- que s'ils sont mal préparés, peuvent retarder la livraison.

## Vue d'ensemble (en pyramide)

```
  ACCEPTATION
       ↑
    SYSTÈME
       ↑
  INTÉGRATION
       ↑
   UNITAIRES
```

**Plus on monte** :
- plus les tests sont **lents et coûteux**,
- mais plus ils **reflètent la réalité utilisateur**.

---

> ℹ️ Dans le cours suivant, vous découvrirez les [différents types de test](./02_types_de_tests.md) (fonctionnels, non-fonctionnels, régressions, ...)
