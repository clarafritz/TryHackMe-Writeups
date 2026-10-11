# Writeup TryHackMe : Windows Basics

- **Parcours :** Pre-Security
- **Date :** 11/10/2026
- **Module :** 3) Operating Systems Basics 
- **Niveau :** Facile / Débutant

---

## Objectifs de la Room
Découvrir l'environnement d'exploitation **Windows Server 2019**, ses composants d'interface principaux (Bureau, Menu Démarrer, Barre des tâches) et la gestion de ses fichiers. Se familiariser avec les outils d'administration et de sécurité natifs (Paramètres, Panneau de configuration, Gestionnaire des tâches, Sécurité Windows / Defender). Exécuter l'installation d'une application et effectuer une analyse antivirus personnalisée.

---

## Notions Clés

  - **Interface utilisateur & Navigation :**
    - *Bureau & Barre des tâches :* Zone de travail principale regroupant les raccourcis, la recherche, la vue des tâches et les icônes de notification.
    - *Menu Démarrer :* Point d'accès centralisé aux applications, paramètres et options d'alimentation.
  - **Gestion de la configuration :**
    - *Paramètres Windows :* Interface moderne centralisant la configuration système, réseau, langue et sécurité.
    - *Panneau de configuration :* Interface héritée pour les outils d'administration avancés (ex. Désinstaller un programme).
  - **Supervision & Sécurité :**
    - *Gestionnaire des tâches :* Outil de suivi en temps réel des processus, performances CPU/RAM, utilisateurs connectés et services.
    - *Sécurité Windows (Windows Defender) :* Protection antivirus intégrée proposant l'analyse en temps réel, l'analyse personnalisée et la gestion du pare-feu.
  - **Authentification & Privilèges :** Distinction entre compte Invité, Standard et Administrateur (compte à contrôle total).

---

## Synthèse des commandes & Pratique (Simulateur)

Au cours de cet atelier pratique sur un poste **Windows Server 2019**, nous avons effectué les actions suivantes :
  1. **Analyse des spécifications système :**
     - Consultation de la section *About your PC* pour identifier le nom de l'appareil (`TB1008`), la mémoire RAM (`4.00 GB`) et la version du système (`1809`).
  2. **Exploration du système de fichiers & Installation d'application :**
     - Navigation dans le répertoire `C:\Users\Administrator\Desktop\TryHatMe Onboarding`.
     - Lecture du fichier `Welcome.txt` pour obtenir le premier drapeau.
     - Exécution de l'installeur `TryHatMeWelcome.exe` pour obtenir le drapeau de confirmation d'installation.
  3. **Supervision et sécurité :**
     - Inspection de la section *Heure et langue* (configuration région : `United States`).
     - Vérification du compte actif via l'onglet *Utilisateurs* du Gestionnaire des tâches (`Administrator`).
     - Lancement d'une analyse personnalisée avec **Sécurité Windows** sur le dossier d'embarquement, détectant un fichier de test inoffensif (`virus:DOS/EICAR_Test_File` lié au fichier `eicar.com.txt`).
