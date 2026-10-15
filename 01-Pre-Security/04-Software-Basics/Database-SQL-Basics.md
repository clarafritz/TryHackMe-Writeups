
# Writeup TryHackMe : Bases des bases de données SQL (Database SQL Basics)

- **Parcours :** Pre-Security
- **Date :** 15/10/2026
- **Module :** 4) Software Basics
- **Niveau :** Facile / Easy

---

## Objectifs de la Room
Comprendre le rôle des bases de données relationnelles dans le stockage et l'organisation des informations. Apprendre la structure élémentaire d'une base de données (tables, lignes, colonnes) et s'initier à l'écriture de requêtes SQL simples pour lire, filtrer et trier des données.

---

## Notions Clés

  - **Structure d'une Base de Données :**
    - **Table (Tableau) :** Structure organisée sous forme de feuille de calcul contenant un ensemble de données liées (ex. `Orders`, `Menu`).
    - **Colonne (Column) :** Définit le type ou la catégorie d'information stockée (ex. `id`, `drink`, `price`, `time`).
    - **Ligne (Row / Enregistrement) :** Représente une entrée complète et unique dans la table (ex. une commande spécifique).

  - **Requêtes SQL (Structured Query Language) :**
    - `SELECT` : Spécifie les colonnes à afficher. Le symbole joker `*` permet de sélectionner **toutes** les colonnes.
    - `FROM` : Indique la table source à interroger (ex. `FROM Orders`).
    - `WHERE` : Applique un filtre sur les lignes selon une condition précise (ex. `WHERE drink = 'Coffee'`).
    - `ORDER BY` : Trie les résultats selon une colonne. Par défaut le tri est croissant (`ASC`), l'ajout de `DESC` permet d'obtenir un tri décroissant (ex. `ORDER BY price DESC`).

---

## Synthèse des commandes & Pratique

Exercices pratiques sur l'interface **Café SQL**
