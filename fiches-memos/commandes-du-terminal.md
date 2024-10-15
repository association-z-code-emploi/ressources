---
tags:
  - cheatsheet
  - terminal
---

# Fiche Mémo des Commandes Courantes

| **Action**                          | **Shell (Linux/Mac)**    | **Windows (PowerShell)**                               |
| ----------------------------------- | ------------------------ | ------------------------------------------------------ |
| Afficher le répertoire actuel       | `pwd`                    | `Get-Location`                                         |
| Lister les fichiers                 | `ls`                     | `Get-ChildItem` ou `dir`                               |
| Changer de répertoire               | `cd nom_du_dossier`      | `Set-Location nom_du_répertoire`                       |
| Créer un répertoire                 | `mkdir nom_du_dossier`   | `New-Item -ItemType Directory -Name nom_du_répertoire` |
| Supprimer un fichier                | `rm nom_du_fichier`      | `Remove-Item nom_du_fichier`                           |
| Supprimer un répertoire             | `rm -r nom_du_dossier`   | `Remove-Item -Recurse nom_du_répertoire`               |
| Copier un fichier                   | `cp source destination`  | `Copy-Item source -Destination destination`            |
| Déplacer un fichier                 | `mv source destination`  | `Move-Item source -Destination destination`            |
| Afficher le contenu d'un fichier    | `cat nom_du_fichier`     | `Get-Content nom_du_fichier`                           |
| Trouver un fichier                  | `find . -name "fichier"` | `Get-ChildItem -Recurse -Filter "fichier"`             |
| Afficher l'historique des commandes | `history`                | `Get-History`                                          |
| Exécuter un script                  | `bash script.sh`         | `.\script.ps1`                                         |
| Afficher l'aide d'une commande      | `man commande`           | `Get-Help commande`                                    |
| Quitter le terminal                 | `exit`                   | `exit`                                                 |

## Notes

- "`nom_du_dossier`", "`nom_du_fichier`", "`fichier`", "`source`", "`destination`", "`commande`" sont des faux noms pour l'exemple : remplacez-les par le dossier, le fichier, les sources et destinations ou les noms de commande qui vous intéresse
- Dans PowerShell, il faut parfois précéder les commandes de `.\` pour les exécuter (eg. `Set-Location .\Documents`)
- Certaines commandes demandent des droits d’administrateur
