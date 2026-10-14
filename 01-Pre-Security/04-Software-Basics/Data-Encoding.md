# Writeup TryHackMe : Encodage des données (How Data is Encoded)

- **Parcours :** Pre-Security
- **Date :** 14/10/2026
- **Module :** 4) Software Basics
- **Niveau :** Facile / Débutant

---

## Objectifs de la Room
Comprendre comment les caractères textuels, symboles et émoticônes sont traduits et stockés sous forme numérique en mémoire. Explorer la norme ASCII, ses limitations, ainsi que le standard universel Unicode et ses différentes formes d'encodage (UTF-8, UTF-16, UTF-32).

---

## Notions Clés

  - **Norme ASCII (American Standard Code for Information Interchange) :**
    - Standard initial sur 7 bits représentant 128 caractères (0 à 127) : alphabet anglais, chiffres, ponctuation de base et caractères de contrôle (ex. saut de ligne, `DEL`, `BEL`).
    - Exemples : `@` = `64` / `65` = `A` / `#` = `35` / `7` = `BEL` (Bell).
    - **ASCII étendu / Normes ISO-8859 :** Utilise un 8ᵉ bit pour offrir 128 caractères supplémentaires adaptés aux langues régionales (ex. ISO-8859-1 pour l'Europe occidentale, ISO-8859-2 pour l'Europe centrale/orientale). Risque de "charabia" (mojibake) si l'encodage de lecture ne correspond pas à l'encodage d'écriture.

  - **Standard Unicode :**
    - Norme universelle attribuant un point de code unique (`Point de Code` / `Code Point`, noté `U+XXXX`) à chaque caractère ou symbole de toutes les langues écrites, actuelles ou anciennes, ainsi qu'aux émoticônes et symboles divers.
  
  - **Formes d'encodage Unicode :**
    - **UTF-8 :** Encodage de longueur variable (1 à 4 octets). Très optimisé pour le Web, rétrocompatible à 100 % avec l'ASCII (1 octet pour les caractères ASCII).
    - **UTF-16 :** Encodage de longueur variable (2 ou 4 octets / 16 bits). Utilisé en interne par de nombreux systèmes d'exploitation (Windows, Java).
    - **UTF-32 :** Encodage fixe à 4 octets (32 bits) par caractère. Très simple à traiter en mémoire mais plus gourmand en espace de stockage.

---

## Synthèse des conversions & Pratique

Au cours de cet atelier pratique, nous avons manipulé les convertisseurs ASCII et Unicode :
  1. **Analyse de la table ASCII :**
     - Identification du code décimal pour `@` : **64**.
     - Recherche du symbole correspondant au code décimal `35` : **`#`**.
     - Identification du nom du caractère spécial pour le code décimal `7` : **`BEL`** (ou Bell / Signal sonore).
  2. **Exploration Unicode et encodages UTF :**
     - Détermination du code UTF-32 de l'émoticône 😌 (`U+0001F60A`).
     - Identification de l'encodage UTF-16 pour le caractère japonais シ (`U+30B7`).
     - Correspondance des points de code Unicode pour les pièces d'échecs :
       - `U+2615` $\rightarrow$ ☕ (Tasse / Boisson chaude) / `U+265E` $\rightarrow$ ♞ (Cavalier noir).
       - `U+2658` $\rightarrow$ ♘ (Cavalier blanc).
