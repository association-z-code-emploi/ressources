---
tags:
  - tutorials
  - test
  - istqb
---

# Les types de tests

Les types de test répondent à la question : “Qu’est-ce qu'on veut évaluer ?”

## Les tests fonctionnels

Ils vont vérifier que le système fait ce qu’il est censé faire, selon les spécifications fonctionnelles. En d’autres termes : on teste les fonctionnalités visibles par l’utilisateur.

**Par exemple**
- le bouton “Connexion” ouvre bien la session
- le panier affiche le bon total
- une API renvoie les bonnes données JSON
- ...

Les **avantages** sont :

- d'être directement reliés aux besoins utilisateurs,
- et de vérifier la conformité aux exigences métier.

Les **limites** sont qu'ils ne disent rien sur la performance, la sécurité ou la robustesse.

## Les tests non-fonctionnels

Ils permettent d'évaluer comment le système fonctionne plutôt que ce qu’il fait. On mesure donc la qualité du comportement.

Les **catégories principales** des tests non-fonctionnels sont :

| Sous-type                  | Objectif                                     | Exemple                                            |
| -------------------------- | -------------------------------------------- | -------------------------------------------------- |
| **Performance**            | Vérifier la rapidité et la stabilité         | Le site supporte 10 000 utilisateurs simultanés    |
| **Sécurité**               | Vérifier la résistance aux attaques          | Injection SQL, XSS, vol de session                 |
| **Compatibilité**          | Tester sur divers navigateurs, OS, appareils | Le site fonctionne sur Chrome, Firefox, mobile     |
| **Utilisabilité (UX)**     | Vérifier la facilité d’usage                 | L’utilisateur comprend le bouton “Acheter”         |
| **Fiabilité / Robustesse** | Vérifier la stabilité                        | L’app ne plante pas après 100 cycles d’utilisation |

Les **avantages** sont :

- de permettre d’assurer la qualité globale du produit,
- d'être souvent déterminant pour la satisfaction utilisateur.

## Les tests de régression

Ils vérifient qu’une modification du code (nouvelle fonctionnalité, correctif, refactorisation) n’a pas introduit de bug dans les parties existantes - "ce qui marchait avant doit encore marcher".

**Par exemple** :

Après avoir ajouté un bouton “supprimer une tâche”, on vérifie que “ajouter une tâche” fonctionne toujours.

Les **avantages** sont :

- de préserver la stabilité du code sur la durée,
- et de s’intègrer facilement dans les pipelines automatisés.

Les **limites** sont :

- qu'ils peuvent devenir longs à exécuter,
- et qu'ils nécessitent une maintenance continue des scripts de test.

## Autres types importants

| Type                                     | Objectif                                                             | Exemple concret                                                           |
| ---------------------------------------- | -------------------------------------------------------------------- | ------------------------------------------------------------------------- |
| **Test de fumée (Smoke Test)**           | Vérifier rapidement que le système démarre et fonctionne globalement | L’appli s’ouvre, la page d’accueil se charge, la base répond              |
| **Test de validation**                   | Confirmer que les exigences du client sont respectées                | Le prix s’affiche toujours en euros sur le site européen                  |
| **Test de vérification**                 | Confirmer que chaque spécification technique est respectée           | Le bouton “Submit” appelle bien l’API `/submitForm`                       |
| **Test exploratoire**                    | Explorer librement pour trouver des défauts non prévus               | Le testeur “joue” avec l’appli pour détecter des comportements inattendus |
| **Test d’acceptation utilisateur (UAT)** | Vérifier que le produit est prêt pour la mise en production          | Le client valide le parcours d’achat complet                              |
| **Test de maintenance**                  | Tester après un changement ou une migration                          | Mise à jour du serveur Node.js sans casser le front-end                   |

## En résumé

| Catégorie                              | Objectif principal                                   | Réalisé par          |
| -------------------------------------- | ---------------------------------------------------- | -------------------- |
| **Fonctionnel**                        | Vérifier que le système *fait ce qu’il doit faire*   | Devs + Testeurs      |
| **Non-fonctionnel**                    | Vérifier *comment* le système le fait                | Testeurs spécialisés |
| **Régression**                         | S’assurer qu’aucun comportement ancien n’a été cassé | Devs + QA            |
| **Exploratoire / Acceptation / Fumée** | Valider la qualité et la stabilité globale           | QA + Utilisateurs    |

---

> [🚧 EN CONSTRUCTION 🚧]
>
> ℹ️ Dans le cours suivant, vous découvrirez le [cycle de vie du test et ses processus](./03_cycle_de_vie_du_test.md) (V-Model, Agile, CI/CD).
