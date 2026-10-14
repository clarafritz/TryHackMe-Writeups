# Writeup TryHackMe : Python: Simple Demo

- **Parcours :** Pre-Security
- **Date :** 14/10/2026
- **Module :** 4) Software Basics
- **Niveau :** Facile / Débutant

---

## Objectifs de la Room
Comprendre les fondements de la programmation impérative en Python à travers la réalisation d'un mini-jeu interactif ("Devinez le nombre"). Apprendre à manipuler les variables, les fonctions d'entrée/sortie, les conversions de types, les structures conditionnelles et les boucles d'itération.

---

## Notions Clés

  - **Variables & Entrées/Sorties :**
    - `print()` : Fonction permettant d'afficher du texte ou des valeurs dans la console.
    - `input()` : Fonction permettant de capturer la saisie de l'utilisateur sous forme de chaîne de caractères (`string`).
    - `int()` : Fonction de conversion (`casting`) pour transformer une chaîne de texte en nombre entier.
    - `random.randint(a, b)` : Méthode de la bibliothèque `random` générant un nombre entier aléatoire compris entre `a` et `b`.

  - **Instructions Conditionnelles (`if`, `elif`, `else`) :**
    - Permettent d'exécuter différents blocs de code selon des conditions logiques.
    - `if` : Évalue la première condition.
    - `elif` (contraction de *else if*) : Évalue une condition alternative si la précédente est fausse.
    - `else` : Exécuté si aucune des conditions précédentes n'est remplie.

  - **Itérations & Boucle `while` :**
    - `while CONDITION:` : Répète un bloc de code temps que la condition spécifiée reste vraie.
    - Opérateur d'inégalité `!=` : Vérifie que deux valeurs sont différentes (ex. `while guess != secret:`).
    - L'indentation (espaces au début de ligne) est obligatoire en Python pour définir les blocs de code appartenant aux boucles et aux conditions.

---

## Synthèse des commandes & Pratique

Au cours de cet atelier pratique, nous avons construit et analysé le script `guess_v3.py` :
  1. **Fonctions de base :**
     - Affichage de texte à l'écran : **`print`**.
     - Conversion d'une saisie utilisateur en entier : **`int`**.
  2. **Contrôle du flux :**
     - Mot-clé pour l'instruction *else if* en Python : **`elif`**.
     - Résultat pour une saisie hors limites (ex. `50`) : **`That number is out of range. Try again.`**
  3. **Itération & Boucle :**
     - Type de boucle utilisé pour répéter le jeu : **`while`**.
     - Résultat affiché en cas de victoire en 3 essais : **`You got it in 3 tries!`** 
