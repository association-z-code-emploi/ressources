---
tags:
  - tutorials
  - java
---

# Travailler avec des fichiers

On utilise différents packages et classes pour lire, écrire et manipuler des données, comme par exemple, le package `java.io`. On parle d'**input** pour une **entrée**, ce qu'on **lit** (eg. lire un fichier), et on parle d'**output** pour une **sortie**, ce qu'on **écrit** (eg. afficher à l'écran).

Les données viennent ou vont vers des endroits comme :

- des fichiers
- des connexions réseau
- des buffers en mémoire (variable, array, ...)
- des flux système (`System.in`, `System.out`, ...)
- etc...

Dans ce cours, on se concentra sur les classes de `java.io` pour les **fichiers**.

## `File`

Pour obtenir des **informations** sur un **fichier**/**dossier** :

```java
import java.io.File;

public class InfosFichier {
  public static void main(String[] args) {
    File monCV = new File(cv.txt);
    System.out.println("Nom : " + monCV.getName());
    System.out.println("Taille : " + monCV.length() + " octets");
    System.out.println("Existe ? " + monCV.exists());

    File dossierPerso = new File("perso");
    String[] fichiers = dossierPerso.list();
  }
}
```

## `FileWriter` et `FileReader`

Pour **écrire** et **lire** des **fichiers textes** :

```java
import java.io.FileWriter;
import java.io.FileReader;
import java.io.IOException;

public class monCV {
  public static void main(String[] args) throws IOException {
    FileWriter ecriture = new FileWriter("monCV.txt");
    ecriture.write("Jim Feddy");
    ecriture.close();

    FileReader lecture = new FileReader("monCV.txt");
    int caractere;
    // read() commence au premier caractère du fichier
    while((caractere = lecture.read()) != -1) {
      System.out.print((char) caractere);
    }
    reader.close();
  }
}
```

> ⚠️ Il faut toujours "ouvrir" et "fermer" ces classes ; comme avec `Scanner` !

> ℹ️ Il existe aussi `FileOutputStream` et `FileInputStream` pour **écrire** et **lire** des **fichiers binaires** (images, vidéos, ...).

## `RandomAccessFile`

Pour accéder à n'**importe quelle endroit** où l'on veut **écrire** ou **lire** dans un **fichier** :

```java
import java.io.RandomAccessFile;

public class changerMonCV {
  public static void main(String[] args) {
    RandomAccessFile fichier = new RandomAccessFile("monCV.txt", "rw";) // "r" pour "read" et "w" pour "write"

    fichier.seek(8); // pour aller au 9ème caractère du fichier
    fichier.writeBytes(" - Web Dev"); // pour écrire à cet endroit

    fichier.seek(0); // pour "revenir" au premier caractère
    System.out.println(fichier.readLine()); // pour lire toute la première ligne

    fichier.close();
  }
}
```

---

## Exercices

Les exercices [12_manipulations_de_fichiers](https://github.com/association-z-code-emploi/exercices-java/tree/main/12_manipulations_de_fichiers) sont recommandés pour pratiquer les (et décrouvrir d'autres) notions vues durant ce cours.
