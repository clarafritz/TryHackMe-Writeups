# Writeup TryHackMe : Data Representation

- **Parcours :** Pre-Security
- **Date :** 14/10/2026
- **Module :** 4) Software Basics
- **Niveau :** Facile / Débutant

---

## Objectifs de la Room
Comprendre comment les ordinateurs représentent les données numériques et visuelles en mémoire à l'aide d'états binaires. Maîtriser le fonctionnement des différents systèmes de numération (décimal, binaire, hexadécimal, octal) et la codification des couleurs au format RVB (RGB).

---

## Notions Clés

  - **Systèmes de numération :**
    - **Binaire (Base 2) :** Utilise uniquement les chiffres `0` et `1` (bits). C'est le langage fondamental des ordinateurs, correspondant à des états électroniques (bas/haut).
    - **Décimal (Base 10) :** Système usuel basé sur les chiffres de `0` à `9`.
    - **Hexadécimal (Base 16) :** Utilise les chiffres de `0` à `9` et les lettres `A` à `F` ($A=10, B=11, C=12, D=13, E=14, F=15$). Chaque chiffre hexadécimal représente exactement un groupe de 4 bits (un nibble).
    - **Octal (Base 8) :** Utilise les chiffres de `0` à `7`. Chaque chiffre octal représente un groupe de 3 bits.
  - **Représentation des couleurs :**
    - **Modèle RVB / RGB :** Combinaison de trois canaux de lumière (Rouge, Vert, Bleu).
    - **Modèle 8 couleurs (3 bits) :** 1 bit par canal ($2^3 = 8$ combinaisons possibles, ex. `000` pour le noir, `111` pour le blanc).
    - **Vraies couleurs (24 bits / 3 octets) :** Chaque canal (R, V, B) est codé sur 8 bits (1 octet), soit 256 valeurs d'intensité possibles par couleur. Cela offre $256 \times 256 \times 256 \approx 16,7$ millions de couleurs uniques.
    - **Format Hexadécimal des couleurs :** Représenté sous la forme `#RRGGBB` où chaque paire hexadécimale correspond à 1 octet (ex. `#FF0000` pour le rouge pur).

---

## Synthèse des commandes & Pratique (Simulateur)

Au cours de cet atelier pratique, nous avons converti des valeurs à l'aide des convertisseurs de base et de couleurs :
  1. **Analyse de la représentation des couleurs :**
     - Conversion du code hexadécimal `#3BC81E` pour identifier sa teinte visuelle (Vert).
     - Décomposition du code `#EB0037` en binaire : $EB = 11101011$, $00 = 00000000$, $37 = 00110111$ ($\rightarrow$ `11101011 00000000 00110111`).
     - Conversion du code `#D4D8DF` en représentation décimale ($R=212, G=216, B=223$).
  2. **Conversions de bases numériques :**
     - Conversion de la valeur hexadécimale `FF` en binaire : $F = 1111$, donc $FF =$ `11111111`.
     - Conversion de la valeur hexadécimale `AB` en décimal : $A \times 16^1 + B \times 16^0 = 10 \times 16 + 11 = 171$.
     - Conversion de la valeur hexadécimale maximale sur 24 bits (`FF FF FF`) en décimal : $16\,777\,215$ (soit **17 millions** arrondi au million le plus proche).
