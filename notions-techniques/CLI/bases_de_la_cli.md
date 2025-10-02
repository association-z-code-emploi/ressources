---
tags:
  - tutorials
  - cli
---

# Bases de la CLI

## Sommaire

- [Qu’est-ce que la CLI et pourquoi l’utiliser ?](#quest-ce-que-la-cli-et-pourquoi-lutiliser-)
- [Naviguer dans le système de fichiers et de dossiers](#naviguer-dans-le-système-de-fichiers-et-de-dossiers)
- [Manipuler des fichiers et dossiers](#manipuler-des-fichiers-et-dossiers)
- [Lire et manipuler le contenu des fichiers](#lire-et-manipuler-le-contenu-des-fichiers)
- [Gestion des processus et programmes](#gestion-des-processus-et-programmes)
- [Personnalisation et scripts simples](#personnalisation-et-scripts-simples)
- [Aller plus loin](#aller-plus-loin)

## Qu’est-ce que la CLI et pourquoi l’utiliser ?

La **CLI (Command Line Interface)** est une interface où l’on écrit du texte (des commandes) pour dire à l’ordinateur ce qu’il doit faire.

Contrairement à une interface graphique (où l'on clique sur des boutons et menus), ici on tape une **commande** et l’ordinateur l’exécute directement.

### Exemple concret

- pour aller dans un dossier via une interface graphique → on clique sur des icônes
- avec la CLI → on écrit `cd Documents` et on y est directement !

**Avantage** : rapidité, puissance, possibilité d’automatiser avec des scripts
**Inconvénient** : il faut retenir ou rechercher les commandes, pas d’icônes visuelles

> ℹ️ Pourquoi les pros (ie. développeurs, administrateurs systèmes, etc...) préfèrent souvent la CLI à l’interface graphique ? Pour sa rapidité et ses automatisations possibles.

### Mini-exercice

Ouvrez un terminal sur votre ordinateur (si vous êtes sous macOS ou Linux, vous avez déjà une app “Terminal”, sous Windows vous pouvez utiliser “PowerShell” ou “Windows Terminal”).

Puis tapez la commande :

```shell
echo "Hello, CLI!"
```

Cette commande affiche simplement du texte dans le terminal !

---

## Naviguer dans le système de fichiers et de dossiers

### Dossier courant

Pour utiliser la CLI efficacement, il faut savoir où vous êtes et vous déplacer dans les dossiers.

Chaque fois que vous ouvrez un terminal, vous vous trouvez dans un dossier courant (ie. votre "emplacement actuel"). Les dossiers et fichiers forment un ensemble relié (ie. une "arborescence") et pour s’y déplacer, on utilise quelques commandes de base :

- `pwd` → affiche le dossier courant (où vous êtes)

  - exemple : `/Users/votre_nom/Documents`

- `ls` → liste le contenu du dossier courant (fichiers et dossiers)

  - exemple : `Documents Images Musique Projets`

- `cd nom_dossier` → change de dossier (descend dans l’arborescence)

  - exemple : `cd Documents`

- `cd ..` → remonte d’un niveau (on revient en arrière, dans le dossier précédent)

> ❓ Imaginons un ordinateur comme une bibliothèque :
>
> - le dossier courant = la salle dans laquelle on se trouve
> - `ls` = on regarde autour de nous et on verra toutes les étagères de la salle
> - `cd` = on marche vers une autre salle
> - `pwd` = on regarde le panneau sur la porte pour savoir dans quelle salle on se trouve

### Pop-quiz !

- Si on se trouve dans `Documents/Projets/SiteWeb` et que l'on tape `cd ..`, où va-t'on se retrouver ?

<!-- ↳ dans le dossier `Projets`, car `cd ..` signifie "revenir au dossier parent/précédent" -->

- Si `Documents` contient les dossiers `Cours Exercices Projets`, quelle commande doit-on taper pour aller, depuis `Documents`, dans le dossier `Exercices` ?

<!-- ↳ on tapera `cd Exercices` puisque c'est un dossier contenu dans `Documents` -->

### Mini-exercice

Effectuez l'exercice [01_variables](https://github.com/association-z-code-emploi/exercices-cli/tree/main/01_navigation_fichiers_et_dossiers/README.md) pour pratiquer les notions vues durant cette section.

---

## Manipuler des fichiers et dossiers

Maintenant que l'on sait se déplacer, il faut apprendre à **créer, déplacer, renommer et supprimer** des fichiers et dossiers :

1. `mkdir nom_dossier` → crée un nouveau dossier

   - exemple : `mkdir Exercices`

2. `touch nom_fichier` → crée un nouveau fichier vide

   - exemple : `touch index.html`

3. `mv fichier destination` → déplace ou renomme un fichier

   - exemple :

     - pour déplacer : `mv index.html Exercices/`
     - pour renommer : `mv index.html accueil.html`

4. `cp fichier destination` → copie un fichier

   - exemple : `cp accueil.html Exercices/`

5. `rm fichier` → supprime un fichier

   - exemple : `rm accueil.html`

6. `rmdir nom_dossier` → supprime un dossier **vide** (pour supprimer un dossier rempli, on utilise `rm -r dossier`)

### Pop-quiz !

- Quelle commande utiliseriez-vous pour **créer un dossier "ProjetSite"** dans votre dossier actuel ?
- Et si on voulait créer directement un fichier `style.css` à l’intérieur de ce dossier, comment s'y prendrait-on ?

### Mini-exercice

Effectuez l'exercice [02_manipulation_fichiers_et_dossiers](https://github.com/association-z-code-emploi/exercices-cli/tree/main/02_manipulation_fichiers_et_dossiers/README.md) pour pratiquer les notions vues durant cette section.

---

## Lire et manipuler le contenu des fichiers

Maintenant qu’on sait créer et organiser des fichiers, voyons comment **les ouvrir et lire leur contenu directement depuis la CLI** :

1. `cat fichier.txt` → affiche le contenu du fichier d’un coup

   - exemple : `cat README.md`

2. `less fichier.txt` → permet de lire le fichier page par page

   - flèches pour naviguer
   - `q` pour quitter

3. `head fichier.txt` → affiche seulement le début (par défaut 10 lignes)

   - exemple : `head -n 5 fichier.txt` → affiche 5 lignes

4. `tail fichier.txt` → affiche la fin (par défaut 10 lignes)

   - exemple : `tail -n 20 fichier.txt` → affiche les 20 dernières lignes

### Pop-quiz

- Si on souhaite lire seulement les **15 premières lignes** d’un fichier `log.txt`, quelle commande utiliserait-on ?
- Si un fichier est énorme (par exemple plusieurs milliers de lignes), pourquoi `less` est-il plus pratique que `cat` ?

### Mini-exercice

Effectuez l'exercice [03_lecture_et_manipulations_fichiers](https://github.com/association-z-code-emploi/exercices-cli/tree/main/03_lecture_et_manipulations_fichiers/README.md) pour pratiquer les notions vues durant cette section.

---

## Gestion des processus et programmes

Une autre utilisation très courante de la CLI est de pouvoir **lancer, lister et arrêter des programmes** :

1. **lancer un programme**

   - exemple : `myProgram &` → lance myProgram en arrière-plan (`&` permet de garder le terminal libre)

2. **lister les processus**

   - `ps` → liste les processus en cours (liés au terminal)
   - `ps aux` → liste _tous_ les processus (plus détaillé)
   - `top` → affiche en direct la consommation CPU/mémoire

3. **arrêter un processus**

   - `kill <PID>` → tue le processus dont tu connais le PID (Process ID).
   - exemple : `kill 12345`

   > ⚠️ Attention à ne pas arrêter certains programmes nécessaires au bon fonctionnement de votre ordinateur ! Contentez-vous d'abord des exercices pour le moment.

### Pop-quiz

- Que fait le symbole `&` à la fin d’une commande ?
- Si on voit dans `ps` un processus avec le PID **5432**, quelle commande taperait-on pour l’arrêter ?

### Mini-exercice

Effectuez l'exercice [04_gestion_processus_et_programmes](https://github.com/association-z-code-emploi/exercices-cli/tree/main/04_gestion_processus_et_programmes/README.md) pour pratiquer les notions vues durant cette section.

---

## Personnalisation et scripts simples

Pour terminer sur les bases de la CLI, voyons comment **commencer à automatiser des tâches** :

1. **variables d’environnement**

   - elles stockent des informations utilisées par le système
   - exemple : `echo $HOME` → affiche le dossier utilisateur
   - exemple : `echo $PATH` → liste les emplacements où le terminal cherche des programmes

2. **scripts shell simples**

   - un script est un fichier texte contenant une série de commandes shell que l’on pourrait taper à la main, mais automatisées pour être réutilisées facilement

     - exemple pour crée un fichier `setup.sh` :

     - on crée un fichier contenant le script :

     ```bash
     #!/bin/bash
     mkdir ProjetWeb
     cd ProjetWeb
     touch index.html style.css README.md
     echo "Projet initialisé !"
     ```

     > ℹ️ `#!/bin/bash` indique quel interpréteur utiliser : ici "bash", mais ça pourrait être "sh", "zsh", ..., selon le shell que vous voulez utiliser

     - puis, pour le rendre exécutable :

     ```
     chmod +x setup.sh
     ```

     - et enfin, pour le lancer :

     ```
     ./setup.sh
     ```

### Pop-quiz

- quelle commande permettrait d’afficher l'emplacement du dossier "utilisateur" via une variable d’environnement ?
- si on écrit un petit script `custom_script.sh` et qu'on veut le rendre exécutable, quelle commande devrait-on taper ?

### Mini-exercice

Effectuez l'exercice [05_personnalisation_et_scripts_simples](https://github.com/association-z-code-emploi/exercices-cli/tree/main/05_personnalisation_et_scripts_simples/README.md) pour pratiquer les notions vues durant cette section.

---

## Aller plus loin

Testez votre compréhension et combiner plusieurs concepts avec un petit challenge CLI : [06_mini_projet](https://github.com/association-z-code-emploi/exercices-cli/tree/main/06_mini_projet/README.md)

D'autres sujets à découvrir avec la CLI :

- les pipes
- le `grep`
- les aliases
- ...
