---
tags:
  - tutorials
  - cheatsheets
  - javascript
  - dom
---

# Fiche mémo : fonctions courantes du DOM

> ℹ️ Documentation sur [MDN](https://developer.mozilla.org/fr/docs/Web/API/Document#propri%C3%A9t%C3%A9s).

| **Fonction DOM**                    | **Description**                                                                                                       | **Exemple**                                                          |
| ----------------------------------- | --------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------- |
| `document.querySelector()`          | Sélectionne le premier élément correspondant au sélecteur CSS donné ; utilise les mêmes règles que les sélecteurs CSS | `let elem = document.querySelector('.classe');`                      |
| `document.querySelectorAll()`       | Sélectionne tous les éléments correspondant au sélecteur CSS donné ; utilise les mêmes règles que les sélecteurs CSS  | `let elems = document.querySelectorAll('p');`                        |
| `document.getElementById()`         | Sélectionne un élément par son `id`                                                                                   | `let elem = document.getElementById('monId');`                       |
| `document.getElementsByClassName()` | Sélectionne tous les éléments ayant une classe donnée                                                                 | `let elems = document.getElementsByClassName('maClasse');`           |
| `document.getElementsByTagName()`   | Sélectionne tous les éléments par nom de balise (tag)                                                                 | `let elems = document.getElementsByTagName('div');`                  |
| `element.textContent`               | Récupère ou modifie le texte à l'intérieur d'un élément                                                               | `elem.textContent = 'Nouveau texte';`                                |
| `element.innerHTML`                 | Récupère ou modifie le contenu HTML d'un élément                                                                      | `elem.innerHTML = '<strong>Nouveau contenu</strong>';`               |
| `element.setAttribute()`            | Ajoute ou modifie un attribut d'un élément                                                                            | `elem.setAttribute('class', 'nouvelleClasse');`                      |
| `element.getAttribute()`            | Récupère la valeur d'un attribut d'un élément                                                                         | `let classe = elem.getAttribute('class');`                           |
| `element.removeAttribute()`         | Supprime un attribut d'un élément                                                                                     | `elem.removeAttribute('class');`                                     |
| `element.appendChild()`             | Ajoute un élément enfant à la fin d'un élément parent                                                                 | `parentElem.appendChild(childElem);`                                 |
| `element.removeChild()`             | Supprime un élément enfant d'un élément parent                                                                        | `parentElem.removeChild(childElem);`                                 |
| `element.replaceChild()`            | Remplace un élément enfant par un autre dans l'élément parent                                                         | `parentElem.replaceChild(nouvelElem, ancienElem);`                   |
| `element.classList.add()`           | Ajoute une ou plusieurs classes à un élément                                                                          | `elem.classList.add('classe1', 'classe2');`                          |
| `element.classList.remove()`        | Supprime une ou plusieurs classes d'un élément                                                                        | `elem.classList.remove('classe1');`                                  |
| `element.classList.toggle()`        | Ajoute une classe si elle n'est pas déjà attribuée à l'élément, sinon la supprime                                     | `elem.classList.toggle('active');`                                   |
| `element.style.property`            | Modifie directement le style d'un élément (style "inline")                                                            | `elem.style.backgroundColor = 'blue';`                               |
| `element.addEventListener()`        | Attache un événement à un élément                                                                                     | `elem.addEventListener('click', function() { alert('Clique !'); });` |
| `document.createElement()`          | Crée un nouvel élément HTML                                                                                           | `let newDiv = document.createElement('div');`                        |
| `element.remove()`                  | Supprime un élément du DOM                                                                                            | `elem.remove();`                                                     |
| `element.focus()`                   | Donne le focus à un élément (souvent utilisé pour des formulaires)                                                    | `elem.focus();`                                                      |
