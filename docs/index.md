# Introduction au Langage C

Le langage C est l'un des langages de programmation les plus populaires et les plus puissants. Il est utilisé pour développer des systèmes d'exploitation, des logiciels embarqués, des applications performantes, et bien plus encore.

## Table des Matières

1. [Histoire du C](#histoire-du-c)
2. [Installation d'un Compilateur](#installation-dun-compilateur)
3. [Syntaxe de Base](#syntaxe-de-base)
4. [Variables et Types de Données](#variables-et-types-de-données)
5. [Opérateurs](#opérateurs)
6. [Structures de Contrôle](#structures-de-contrôle)
7. [Fonctions](#fonctions)
8. [Tableaux et Pointeurs](#tableaux-et-pointeurs)
9. [Gestion de la Mémoire](#gestion-de-la-mémoire)
10. [Fichiers](#fichiers)
11. [Exercices](exercices.md)
---

## Histoire du C

Le langage C a été développé dans les années 1970 par Dennis Ritchie au Bell Labs. Il a été conçu pour être un langage de programmation de bas niveau, permettant un contrôle précis du matériel, tout en restant suffisamment abstrait pour être portable.

## Installation d'un Compilateur

Pour écrire et exécuter des programmes en C, vous avez besoin d'un compilateur C. Voici quelques compilateurs populaires :

- **GCC** (GNU Compiler Collection)
- **Clang**
- **MSVC** (Microsoft Visual C++ pour Windows)

Une fois le compilateur installé, vous pouvez créer un fichier avec l'extension `.c`, l'écrire avec du code C, et le compiler avec la commande :

```bash
gcc mon_programme.c -o mon_programme
```

## Syntaxe de Base

Voici un exemple de programme "Hello, World!" en C :

```c
#include <stdio.h>

int main() {
    printf("Hello, World!\n");
    return 0;
}
```

### Explication

- `#include <stdio.h>` : Inclut la bibliothèque standard d'entrée/sortie pour utiliser `printf`.
- `int main()` : Fonction principale qui démarre le programme.
- `printf` : Fonction qui affiche du texte à l'écran.

## Variables et Types de Données

En C, les variables doivent être déclarées avec un type. Voici les types de base :

- `int` : Entier (par exemple, `int a = 5;`)
- `float` : Nombre à virgule flottante (ex. `float b = 5.5;`)
- `char` : Caractère unique (ex. `char c = 'A';`)

Exemple :

```c
#include <stdio.h>

int main() {
    int age = 30;
    float taille = 1.75;
    char initial = 'J';
    
    printf("Age : %d, Taille : %.2f, Initial : %c\n", age, taille, initial);
    return 0;
}
```

## Opérateurs

Les opérateurs en C incluent :

- Opérateurs arithmétiques : `+`, `-`, `*`, `/`, `%`
- Opérateurs de comparaison : `==`, `!=`, `<`, `>`, `<=`, `>=`
- Opérateurs logiques : `&&`, `||`, `!`

Exemple :

```c
int a = 10, b = 5;
int somme = a + b;
int egal = (a == b);
```

## Structures de Contrôle

### Conditionnelles

```c
#include <stdio.h>

int main() {
    int age = 20;

    if (age >= 18) {
        printf("Vous êtes majeur.\n");
    } else {
        printf("Vous êtes mineur.\n");
    }

    return 0;
}
```

### Boucles

- **while** : Répète une action tant qu'une condition est vraie.
- **for** : Répète une action pour un nombre défini d'itérations.

Exemple de boucle `for` :

```c
for (int i = 0; i < 5; i++) {
    printf("i vaut %d\n", i);
}
```

## Fonctions

Les fonctions permettent de structurer le code.

```c
#include <stdio.h>

int addition(int a, int b) {
    return a + b;
}

int main() {
    int resultat = addition(5, 3);
    printf("Le résultat est %d\n", resultat);
    return 0;
}
```

## Tableaux et Pointeurs

### Tableaux

Un tableau est une collection de variables de même type.

```c
int nombres[5] = {1, 2, 3, 4, 5};
printf("Premier élément : %d\n", nombres[0]);
```

### Pointeurs

Les pointeurs sont des variables qui stockent des adresses mémoire.

```c
int a = 5;
int *p = &a;
printf("La valeur de a est %d\n", *p);
```

## Gestion de la Mémoire

En C, vous pouvez allouer et libérer manuellement de la mémoire avec `malloc` et `free`.

```c
#include <stdio.h>
#include <stdlib.h>

int main() {
    int *ptr = malloc(sizeof(int));
    *ptr = 42;
    printf("Valeur : %d\n", *ptr);
    free(ptr); // Libère la mémoire
    return 0;
}
```

## Fichiers

Le C permet la manipulation de fichiers avec des fonctions comme `fopen`, `fprintf`, `fscanf`, etc.

```c
#include <stdio.h>

int main() {
    FILE *fichier = fopen("test.txt", "w");
    if (fichier != NULL) {
        fprintf(fichier, "Bonjour, fichier !");
        fclose(fichier);
    }
    return 0;
}
```