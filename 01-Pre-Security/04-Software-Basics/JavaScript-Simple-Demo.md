# Writeup TryHackMe : JavaScript : Démo simple (JavaScript: Simple Demo)

- **Parcours :** Pre-Security
- **Date :** 15/10/2026
- **Module :** 4) Software Basics
- **Niveau :** Facile / Débutant

---

## Objectifs de la Room
Découvrir les fondamentaux du langage JavaScript et son exécution côté serveur/machine locale via l'environnement Node.js. Mettre en œuvre les concepts fondamentaux de la programmation impérative (variables, constantes, entrées/sorties, conversion de types, structures conditionnelles et boucles d'itération) à travers la création d'un mini-jeu ("Devinez le nombre").

---

## Notions Clés

  - **Exécution & Déclarations de Variables :**
    - `node script.js` : Commande permettant d'exécuter un fichier JavaScript hors navigateur via le moteur Node.js.
    - `let` : Déclare une variable dont la valeur peut réassignée au cours de l'exécution du programme (ex. `let tries = 0;`).
    - `const` : Déclare une constante dont la valeur ne peut pas être modifiée après initialisation (ex. `const secret = 12;`).
    - `console.log()` : Méthode permettant d'afficher des données dans la console.

  - **Génération Aléatoire & Conversion de Types :**
    - `Math.random()` : Génère un nombre décimal pseudo-aléatoire dans l'intervalle $[0, 1[$.
    - `Math.floor()` : Arrondit un nombre à l'entier inférieur. La formule `Math.floor(Math.random() * 20) + 1` génère ainsi un entier entre 1 et 20.
    - `parseInt(text, 10)` : Convertit une chaîne de caractères (`string`) en un entier en base 10.

  - **Conditions & Boucles d'Itération :**
    - `if`, `else if`, `else` : Gèrent les branchements conditionnels (ex. vérification des limites avec l'opérateur logique OU `||`).
    - `while (CONDITION) { ... }` : Exécute en boucle un bloc d'instructions tant que la condition reste vraie.
    - Opérateur d'inégalité stricte `!==` / `!=` : Vérifie que deux valeurs ne sont pas égales (ex. `while (guess !== secret)`).

---

## Synthèse des commandes & Pratique

Au cours de cet atelier pratique, nous avons analysé et exécuté les scripts `guess_v1.js`, `guess_v2.js` et `guess_v3.js` :
  1. **Déclarations et Affichage :**
     - Mot-clé pour déclarer une variable : **`let`**.
     - Mot-clé pour déclarer une constante : **`const`**.
     - Méthode d'affichage dans la console : **`console.log()`**.
  2. **Saisie utilisateur et Conversion :**
     - Méthode utilisée pour convertir la saisie texte en nombre entier : **`parseInt()`**.
  3. **Comportement des Conditions (`secret = 10`) :**
     - Résultat pour une proposition de `15` (`guess > secret`) : **`Too high, try again.`**
     - Résultat pour une proposition de `35` (`guess > 20`) : **`That number is out of range. Try again.`**
  4. **Gestion de la Boucle :**
     - Type de boucle utilisé : **`while`**.
     - Variable incrémentée à chaque essai : **`tries`**.
     - Opérateur utilisé pour exprimer "différent de" : **`!=`** (ou **`!==`**).
