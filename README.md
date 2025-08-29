# get_next_line

get_next_line est un projet en C qui consiste à **lire une ligne complète depuis un fichier** ou un descripteur de fichier, quelle que soit sa longueur.  
L’objectif est de manipuler efficacement les fichiers et la mémoire en utilisant les fonctions de base du langage C.

## Fonctionnalité principale

La fonction principale implémentée est :

```c
char *get_next_line(int fd);
```
Elle lit une ligne à la fois depuis le descripteur de fichier fd.
La ligne inclut le caractère de fin de ligne \n si présent.
Elle retourne NULL lorsque la fin du fichier est atteinte ou en cas d’erreur.

## Contraintes du projet

Fonctions autorisées limitées : seule une petite partie de la libc est utilisable (read, malloc, free, etc.).

Lecture progressive avec BUFFER_SIZE configurable, même si la ligne dépasse cette taille.

Chaque ligne doit être allouée dynamiquement et libérée par l’utilisateur.

Gestion de tous les cas possibles : fichiers vides, fichiers très longs, lignes sans \n.

Ce projet est considéré comme techniquement exigeant pour plusieurs raisons :

Une bonne maîtrise de la gestion dynamique de la mémoire est indispensable pour éviter les fuites.

La lecture progressive des fichiers nécessite une gestion fine des buffers.

Il faut écrire une fonction robuste, capable de gérer tous les cas d’usage possibles.

Compréhension nécessaire des descripteurs de fichiers et des appels système (read, open, close).
