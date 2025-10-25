---
tags:
  - tutorials
  - php
---

# Boucles

Les **boucles** permettent de **répéter du** code tant qu’une condition est **vraie**.

On trouve trois variations :

- `while`
- `for`
- `foreach`

---

## "Tant que ..." : `while`

Elle bouclera un nombre de fois **indéfini** tant que sa condition n'est pas remplie :

```php
$i = 1;
while ($i <= 5) {
  echo "Tour n°$i ";
  $i++;
}
```

---

## "Autant de fois que ..." : `for`

Elle bouclera un nombre de fois défini via un **compteur** , qui pourra être automatiquement modifié en **fin de tour de boucle** :

```php
for ($i = 1; $i <= 5; $i++) {
  echo "Tour n°$i \n";
}
```

- `$i = 1` : départ
- `$i <= 5` : condition de poursuite
- `$i++` : incrémentation à chaque tour

---

## Boucle + tableau : `foreach`

Elle bouclera un nombre de fois équivalent au nombre d'élément dans un **tableau** :

```php
$notes = [12, 5, 7];

foreach($notes as $note) {
  echo $note . "\n";
}
```

---

> ℹ️ Dans le cours suivant, vous découvrirez les [fonctions](./04_fonctions.md) pour répéter une instruction et la réutiliser !

---

## Exercices

Les exercices [03_boucles](https://github.com/association-z-code-emploi/exercices-php/tree/main/03_boucles) sont recommandés pour pratiquer les notions vues durant ce cours.
