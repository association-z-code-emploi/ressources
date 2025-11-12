---
tags:
  - tutorials
  - test
  - istqb
---

# Introduction aux tests logiciels et d'applications

Le **test logiciel et d'application** est un **processus d'évaluation** d'un produit (site, apps, ...) pour vérifier qu'il répond bien aux **exigences** et qu'il fonctionne **comme prévu**.

> ⚠️ Mais attention :
>
> - le test ne prouve pas l'absence de défauts,
> - il permet plutôt de **réduire l'incertitude** et d'**augmenter la confiance** dans la qualité du produit.

## Concepts fondamentaux

| Terme                       | Définition                    | Exemple technique                                      |
| --------------------------- | ----------------------------- | ------------------------------------------------------ |
| **Erreur (_mistake_)**      | Une action humaine incorrecte | Un développeur tape `x = y + 1` au lieu de `x = y - 1` |
| **Défaut (_bug_, _fault_)** | Une anomalie dans le code     | Utiliser la mauvaise formule pour un calcul            |
| **Échec (_failure_)**       | Le résultat final est faux    | L'application affiche un total faux à l'écran          |

> ℹ️ Ces trois notions forment la chaîne :
>
> **Erreur** humaine → **Défaut** dans le code → **Échec** dans le comportement

## Pourquoi tester ?

- Pour détecter les défauts avant que les utilisateurs ne les rencontrent
- Pour garantir la qualité et la conformité aux exigences
- Pour prévenir les régressions lors des mises à jour (ie. ne pas "casser" ce qui existait déjà et ne devrait pas changer)
- Pour améliorer la confiance (client, utilisateur, ...) dans le produit
- Pour réduire les coûts : plus un bug est détecté tôt, moins il coûte cher en temps et en argent à corriger !

> 📝 **Exemple concret** :
>
> Corriger un bug coûte en temps et en argent trouvé :
>
> - 1x pendant le développement,
> - 10x en recette,
> - et 100x en production !

## Activités principales d'un testeur

- Planifier le test (quoi, quand, comment)
- Concevoir les cas de test
- Exécuter les tests
- Consigner les résultats
- Analyser et rapporter les défauts
- Vérifier les corrections

## 7 principes fondamentaux du test (ISTQB Foundation)

L'**[ISTQB](https://istqb.org/)** (en anglais : _International Software Testing Qualifications Board_) est le _Comité international de qualification du test logiciel et d'application_. Il permet de valider un titre de **testeur certifié ISTQB**, une qualification standardisée et reconnue dans le monde entier.

Cette certification aborde 7 principes fondamentaux du test :

1. **Le test montre la présence de défauts, pas leur absence**

Le test permet de révéler des défauts, mais jamais de prouver qu'il n'en reste plus.
Même si tous les tests passent, il peut encore exister des scénarios non testés.

> 📝 **Exemple** :
>
> Une app bancaire passe tous les tests fonctionnels, mais un bug de sécurité subsiste si l'utilisateur copie un script dans le champ de connexion.
>
> ➡ Le test réduit le risque, il ne le supprime pas.

2. **Le test exhaustif est impossible**

Tester toutes les combinaisons possibles de données, chemins ou configurations n'est pas réaliste. Il faut donc prioriser et sélectionner intelligemment les cas de test.

> 📝 **Exemple** :
>
> Si un champ peut contenir 8 caractères alphanumériques, il y a déjà 36⁸ combinaisons possibles - impossible à tester intégralement !
>
> ➡ Utiliser des techniques de conception de tests pour choisir les cas les plus courants.

3. **Tester tôt ("_early testing_")**

Plus on commence à tester tôt dans le cycle de développement, plus on économise du temps et de l'argent.

> 📝 **Exemple** :
>
> Relire une spécification mal écrite avant de coder permet d'éviter des dizaines de bugs plus tard.
>
> ➡ Le test n'attend pas la fin du développement.

4. **Le regroupement des défauts (_defect clustering_)**

Souvent, une petite partie du code contient la majorité des défauts.
Cela suit la loi de Pareto (80/20) : 80 % des bugs viennent de 20 % du code.

> 📝 **Exemple** :
>
> Un module de paiement complexe génère à lui seul la plupart des incidents.
>
> ➡ Concentrer les tests là où le risque et la complexité sont les plus élevés.

5. **Le paradoxe du pesticide (_pesticide paradox_)**

Répéter toujours les mêmes tests finit par ne plus rien détecter de nouveau. Le logiciel "s'immunise" contre ces tests.

> 📝 **Exemple** :
>
> Si on relance les mêmes 20 tests de régression à chaque livraison, on ne découvrira pas les nouveaux types d'erreurs.
>
> ➡ Il faut réviser, renouveler et améliorer les tests régulièrement.

6. **Le test dépend du contexte**

Les méthodes, outils et priorités de test varient selon le type de projet :

- apps critique (eg. aéronautique ou médicale) → tests formels, rigoureux
- apps web agile → tests rapides, automatisés, exploratoires

> ➡ Adapter son approche au risque, au domaine et aux objectifs du projet.

7. **L'illusion d'absence d'erreurs**

Corriger tous les défauts ne garantit pas que le produit sera réussi. Un logiciel peut être "sans bug", mais ne pas répondre aux besoins utilisateurs !

> 📝 **Exemple** :
>
> L'interface est impeccable techniquement, mais illogique pour l'utilisateur final.
>
> ➡ La qualité ne se limite pas à la conformité, mais à la valeur pour l'utilisateur.

## Syllabus ISTQB

Vous retrouverez toute les **informations**, les **concepts** et l'**examen** de la **certification ISTQB Foundation** (le premier niveau) sur le site de l'[ISTQB - Foundation Level](https://istqb.org/certifications/certified-tester-foundation-level-ctfl-v4-0/).

---

> ℹ️ Dans le cours suivant, vous découvrirez les [différents niveaux de test](./01_niveaux_de_tests.md) (unitaires, d'intégrations, etc...).
