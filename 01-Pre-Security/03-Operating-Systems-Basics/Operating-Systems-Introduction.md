# Writeup TryHackMe : Operating Systems Introduction

- **Parcours :** Pre-Security
- **Date :** 11/10/2026
- **Module :** 2) Computer Fundamentals
- **Niveau :** Facile / Débutant

---

## Objectifs de la Room
Comprendre le rôle fondamental d'un système d'exploitation (OS) en tant qu'intermédiaire entre le matériel, les applications et l'utilisateur. Appréhender la séparation des privilèges entre l'espace noyau (kernel space) et l'espace utilisateur (user space). Identifier les différentes familles d'OS (Windows, Linux, macOS, Android/iOS) ainsi que leurs cas d'usage (Desktop, Server, Mobile, Embedded/IoT). Naviguer dans une VM Linux d'inspection pour recueillir des métadonnées système.

---

## Notions Clés

  - **Système d'exploitation (OS) :** Logiciel central coordonnant le matériel, la mémoire, les processus, le système de fichiers, l'authentification et les périphériques.
  - **Couches de privilèges système :**
    - *Espace Noyau (Kernel Space) :* Zone hautement sécurisée hébergeant le noyau, disposant d'un accès direct et illimité au matériel.
    - *Espace Utilisateur (User Space) :* Environnement restreint où s'exécutent les applications classiques. Tout accès matériel nécessite un appel système (*system call*) vers le noyau.
  - **Modes d'interaction :**
    - *GUI (Graphical User Interface) :* Interface visuelle (icônes, fenêtres).
    - *CLI (Command Line Interface) :* Interface textuelle offrant un contrôle précis et rapide du système.
  - **Fonctions de sécurité natives :** Authentification, gestion des autorisations, isolation des processus et protection des fichiers système.

---

## Synthèse des commandes & Pratique (Simulateur)

Dans cette salle, nous avons exploré une machine virtuelle Linux (Ubuntu MATE) pour recueillir des informations système :
  1. **Inspection des spécifications système (GUI) :**
     - Utilisation du raccourci **About This Computer** pour vérifier la version du système.
     - Consultation de l'outil **System Monitor** (onglet *System / Hardware*) pour obtenir la quantité de mémoire RAM allouée.
  2. **Analyse du système de fichiers :**
     - Inspection de l'onglet *File Systems* pour identifier le type d'appareil de la partition racine `/dev/root` (`ext4`).
  3. **Exploration du répertoire `/home` :**
     - Inspection du gestionnaire de fichiers pour recenser les dossiers utilisateurs présents.
     - Lecture du fichier `note.txt` situé dans le dossier `Documents` de l'utilisateur Alex pour extraire le drapeau de validation.
