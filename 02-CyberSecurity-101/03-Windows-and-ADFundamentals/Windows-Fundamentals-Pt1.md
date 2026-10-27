# Writeup TryHackMe : Windows Fundamentals 1

- **Parcours :** Cyber Security 101
- **Date :** 27/10/2026
- **Module :** 3) Windows and AD Fundamentals
- **Niveau :** Facile / Débutant

---

## Objectifs de la Room
Découvrir les fondements du système d'exploitation Windows 10 et Windows Server. Découvrir l'interface graphique (GUI), la structure et le fonctionnement du système de fichiers NTFS, l'organisation du répertoire `System32`, la gestion des comptes et profils utilisateurs, les mécanismes d'autorisations, ainsi que le rôle du contrôle de compte d'utilisateur (UAC), des paramètres système, du Panneau de configuration et du Gestionnaire des tâches.

---

## Notions Clés

- **Éditions & Évolution de Windows :**
  - Différence entre les éditions grand public (Home) et professionnelles/entreprises (Pro), ces dernières incluant des fonctionnalités de sécurité et d'administration avancées (ex. chiffrement BitLocker).
  - Distinction entre les versions de bureau (Windows 10/11) et les versions pour serveurs (Windows Server 2019/2025).

- **Interface Graphique (GUI) & Barre des tâches :**
  - Composants principaux : Bureau, menu Démarrer, zone de recherche, bouton *Task View*, barre des tâches et zone de notification (*System Tray*).
  - Personnalisation de l'affichage, masquage des éléments de recherche et d'affichage des tâches, et gestion des icônes de la zone de notification (ex. réseau, volume, *Action Center*).

- **Système de fichiers NTFS & Permissions :**
  - **NTFS (*New Technology File System*) :** Système de fichiers journalisé supportant les fichiers de plus de 4 Go, le chiffrement EFS et la gestion fine des autorisations d'accès.
  - **Permissions NTFS :** Contrôle d'accès granulaire (Lecture, Écriture, Lecture & Exécution, Modification, Contrôle total) configurable via l'onglet *Sécurité* des propriétés d'un fichier/dossier.
  - **Alternate Data Streams (ADS) :** Attribut propre à NTFS permettant de lier plusieurs flux de données à un seul fichier (utilisé pour identifier l'origine web des téléchargements avec `$DATA`, mais parfois détourné pour dissimuler des données).

- **Répertoires Systèmes Clés :**
  - **`C:\Windows` (variable `%windir%`) :** Répertoire racine du système d'exploitation.
  - **`System32` (`C:\Windows\System32`) :** Contient les utilitaires critiques, les fichiers exécutables du système et les DLL essentielles au fonctionnement du système d'exploitation.

- **Gestion des Utilisateurs & UAC :**
  - **Types de comptes :** Administrateur local (privilèges élevés) et Utilisateur standard (accès restreint). Les profils utilisateurs sont hébergés sous `C:\Users\<username>`.
  - **Outil `lusrmgr.msc` :** Console de gestion des utilisateurs et des groupes locaux (ex. comptes intégrés `Administrator` et `Guest`).
  - **UAC (*User Account Control*) :** Mécanisme de sécurité introduisant une invite de confirmation ou d'élévation de privilèges lorsqu'une application tente d'exécuter des actions nécessitant des droits d'administration (symbole de bouclier).

- **Administration & Outils Système :**
  - **Paramètres & Panneau de configuration :** Centralisent les réglages du système (réseau, comptes, affichage en petites icônes incluant *Windows Defender Firewall*).
  - **Gestionnaire des tâches (*Task Manager*) :** Permet de surveiller les processus actifs, l'utilisation des ressources (CPU, RAM) et les performances du système. Raccourci d'accès : `Ctrl+Shift+Esc`.

---

## Synthèse des commandes & Pratique (Simulateur)

Dans cette salle, nous avons interagi avec une instance distante Windows 10 / Server via RDP et exploré les outils d'administration locaux :

1. **Connexion distante RDP & Analyse du système :**
   - Connexion à la machine de laboratoire avec les identifiants d'administration pour analyser la version du système et tester les droits d'accès.

2. **Exploration du système de fichiers et gestion des permissions :**
   - Inspection du lecteur système `C:` (NTFS).
   - Accès aux propriétés du dossier `Windows` et analyse des autorisations de sécurité attribuées aux groupes `Users`, `Administrators` et `SYSTEM`.
   - Localisation du répertoire `%windir%\System32`.

3. **Gestion des utilisateurs locaux via MMC (`lusrmgr.msc`) :**
   - Lancement de l'exécutable de gestion des utilisateurs :
     ```cmd
     lusrmgr.msc
     ```
   - Inspection des comptes utilisateurs configurés (compte standard `tryhackmebilly`, comptes système intégrés `Administrator` et `Guest`).
   - Analyse de l'appartenance de `tryhackmebilly` aux groupes locaux (`Users`, `Remote Desktop Users`).

4. **Test d'élévation de privilèges & UAC :**
   - Connexion en tant qu'utilisateur standard et tentative d'installation d'un binaire (Wireshark).
   - Observation du comportement du prompt UAC (*User Account Control*) demandant la saisie des identifiants d'un compte administrateur.

5. **Navigation dans le Panneau de Configuration et Gestionnaire des tâches :**
   - Modification de l'affichage du Panneau de Configuration en petites icônes pour repérer des éléments avancés comme *Windows Defender Firewall*.
   - Ouverture du Gestionnaire des tâches via la combinaison de touches `Ctrl+Shift+Esc` pour inspecter la liste des processus en arrière-plan et la consommation mémoire.
