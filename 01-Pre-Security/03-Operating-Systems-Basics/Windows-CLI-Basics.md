# Writeup TryHackMe : Windows CLI Basics

- **Parcours :** Pre-Security
- **Date :** 12/10/2026
- **Module :** 3) Operating Systems Basics
- **Niveau :** Facile / Débutant

---

## Objectifs de la Room
Apprendre à utiliser l'invite de commandes Windows (CMD) pour naviguer dans l'arborescence des fichiers, rechercher des documents spécifiques et collecter des informations système et réseau essentielles. Comprendre les équivalents Windows des commandes d'administration fondamentales.

---

## Notions Clés

  - **Navigation & Gestion de fichiers :**
    - `cd` : Affiche le répertoire courant lorsqu'exécuté seul, ou permet de changer de dossier (ex. `cd Documents`, `cd ..` pour remonter).
    - `dir` : Affiche la liste des fichiers et dossiers du répertoire actuel.
    - `dir /a` : Affiche tous les fichiers et dossiers, y compris les éléments cachés.
    - `type <fichier>` : Affiche le contenu d'un fichier texte directement dans la console (équivalent de `cat` sous Linux).
  - **Recherche :**
    - `dir /s <nom_fichier>` : Recherche récursivement un fichier dans le répertoire courant et tous ses sous-dossiers, puis affiche son chemin d'accès complet.
  - **Inspection Système & Réseau :**
    - `whoami` : Affiche l'utilisateur actuellement connecté.
    - `hostname` : Renvoie le nom réseau de la machine Windows.
    - `systeminfo` : Affiche une analyse détaillée du système (nom/version de l'OS, fabricant, architecture x64/x86, mémoire RAM, correctifs installés).
    - `ipconfig` : Affiche la configuration réseau actuelle (adresse IPv4, masque de sous-réseau, passerelle par défaut).

---

## Synthèse des commandes & Pratique (Simulateur)

Au cours de cet atelier pratique sur un environnement Windows Server 2019, nous avons effectué les étapes suivantes :
  1. **Navigation et localisation de fichier :**
     - Vérification de l'emplacement initial via `cd` (`C:\Users\Administrator`).
     - Utilisation de `dir /s task_brief.txt` pour localiser le fichier dans l'arborescence utilisateur.
     - Déplacement vers le dossier trouvé et affichage du contenu avec `type task_brief.txt` pour lire les consignes de mission.
  2. **Collecte d'informations système et réseau :**
     - Identification de l'utilisateur actif via `whoami` (`administrator`).
     - Vérification du nom d'hôte avec `hostname`.
     - Inspection de la version exacte du système d'exploitation via `systeminfo` (Microsoft Windows Server 2019 Datacenter).
     - Analyse de la connectivité réseau avec `ipconfig` pour récupérer l'adresse IPv4 et la passerelle par défaut.
