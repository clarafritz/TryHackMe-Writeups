# Writeup TryHackMe : Linux CLI Basics

- **Parcours :** Pre-Security
- **Date :** 12/10/2026
- **Module :** 3) Operating Systems Basics
- **Niveau :** Facile / Débutant

---

## Objectifs de la Room
Apprendre à utiliser l'interface en ligne de commande (CLI) sous Linux pour naviguer dans le système de fichiers, rechercher des documents et collecter des informations système clés. Comprendre l'utilité du terminal par rapport à l'interface graphique (GUI) et exécuter des commandes fondamentales d'inspection système.

---

## Notions Clés

  - **Navigation & Gestion de fichiers :**
    - `pwd` (*print working directory*) : Affiche le chemin complet du répertoire courant.
    - `ls` / `ls -l` / `ls -al` : Liste le contenu d'un dossier (fichiers classiques, détails de permissions/tailles, ainsi que les fichiers cachés commençant par un `.`).
    - `cd` : Permet de se déplacer dans l'arborescence (`cd ..` pour remonter d'un niveau).
    - `cat` : Affiche le contenu d'un fichier texte dans le terminal.
  - **Recherche :**
    - `find <chemin> -name <nom_fichier>` : Localise précisément un fichier dans le système de fichiers à partir d'un point de départ (ex. `~` pour le répertoire personnel).
  - **Inspection Système :**
    - `whoami` : Renvoie le nom de l'utilisateur actuellement connecté.
    - `uname -a` : Affiche les informations sur le noyau Linux, la version et l'architecture système.
    - `df -h` : Affiche l'utilisation de l'espace disque dans un format lisible par l'humain (`-h` pour *human-readable*). La ligne `/dev/root` représente le disque principal et la colonne `Avail` indique l'espace libre.
    - `/etc/os-release` : Fichier système contenant les détails de la distribution Linux (ex. Ubuntu 24.04 LTS).

---

## Synthèse des commandes & Pratique (Simulateur)

Au cours de cet atelier pratique, nous avons simulé la prise en main d'un poste de travail Linux :
  1. **Localisation et lecture d'une mission :**
     - Utilisation de `find ~ -name mission_brief.txt` pour trouver le chemin complet du fichier.
     - Déplacement vers le répertoire et lecture du contenu via `cat mission_brief.txt` pour obtenir les premières instructions.
  2. **Collecte d'informations système :**
     - Vérification de l'utilisateur actif avec `whoami` (`ubuntu`).
     - Identification de la version exacte du noyau avec `uname -a` (`6.14.0-1018-aws`).
     - Vérification du stockage principal disponible via `df -h` (colonne `Avail` sur `/dev/root` : `58G`).
     - Lecture des informations sur la distribution dans `/etc/os-release`.
  3. **Résolution du mini-défi :**
     - Localisation du fichier `day1_report.txt` caché dans les sous-dossiers (`~/.logs/archive/day1_report.txt`).
     - Lecture du rapport final avec `cat` pour extraire le mot clé d'achèvement (`END-OF-DAY1`).
