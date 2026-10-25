# Writeup TryHackMe : Linux Fundamentals Pt2

- **Parcours :** Cyber Security 101
- **Date :** 25/10/2026
- **Module :** 2) Linux Fundamentals
- **Niveau :** Facile / Débutant

---

## Objectifs de la Room
Approfondir l'utilisation du système d'exploitation Linux et de son terminal en se connectant à une machine distante via le protocole SSH. Découvrir l'utilisation des options/arguments (comme les pages man et l'option `--help`), maîtriser la gestion avancée des fichiers et répertoires (création, copie, déplacement, suppression), appréhender l'organisation standard du système de fichiers Linux (`/etc`, `/var`, `/tmp`, `/root`) et comprendre la gestion de la propriété et des autorisations d'accès aux fichiers et répertoires, ainsi que l'élévation ou le changement d'utilisateur avec `su` / `sudo`.

---

## Notions Clés

- **Accès à Distance (SSH - Secure Shell) :**
  - **Principe :** Protocole réseau sécurisé et chiffré permettant de prendre le contrôle d'une machine distante en ligne de commande.
  - **Informations requises :** L'adresse IP du serveur cible, le nom d'utilisateur et le mot de passe du compte.
  - **Syntaxe :** `ssh utilisateur@IP_CIBLE` (la saisie du mot de passe s'effectue à l'aveugle dans le terminal par mesure de sécurité).

- **Extension des Commandes & Documentation :**
  - **Arguments & Options :** Modifient le comportement par défaut d'une commande (ex. `-a` pour afficher les fichiers cachés avec `ls`).
  - **Option `--help` :** Fournit un résumé rapide de la syntaxe et des options disponibles pour une commande.
  - **Manuel (`man`) :** Affiche la page de documentation complète d'une commande (ex. `man ls`).

- **Gestion du Système de Fichiers :**
  - **`touch` :** Crée un fichier vide.
  - **`mkdir` :** Crée un répertoire (possibilité de créer des répertoires imbriqués).
  - **`cp` (*Copy*) :** Copie un fichier ou un dossier d'un emplacement à un autre (`cp fichier_source destination`).
  - **`mv` (*Move*) :** Déplace ou renomme un fichier/dossier (`mv ancien_nom nouveau_nom`).
  - **`rm` (*Remove*) :** Supprime un fichier. Utiliser l'option `-r` ou `-R` pour supprimer un répertoire et son contenu de manière récursive.

- **Arborescence et Répertoires Systèmes Clés :**
  - **`/` (Racine) :** Le sommet de l'arborescence du système de fichiers Linux.
  - **`/etc` :** Contient les fichiers de configuration du système et des applications (ex. `sudoers`).
  - **`/var` (*Variable*) :** Stocke les données dynamiques et évolutives du système, notamment les fichiers journaux (`/var/log`).
  - **`/tmp` (*Temporaire*) :** Dossier accessible en écriture à tous les utilisateurs, dont le contenu est vidé à chaque redémarrage.
  - **`/root` :** Répertoire personnel de l'administrateur système (`root`), distinct du dossier `/home`.

- **Autorisations, Propriétaires & Changement d'Utilisateur :**
  - **Droits d'accès :** Chaque fichier/répertoire possède des autorisations distinctes pour la lecture (*r*), l'écriture (*w*) et l'exécution (*x*), réparties entre le propriétaire, le groupe et les autres utilisateurs.
  - **`su` (*Switch User*) :** Permet de basculer vers un autre compte utilisateur (ex. `su - user2` ou `su -l user2`).
  - **`sudo` (*SuperUser Do*) :** Permet d'exécuter des commandes avec les privilèges de l'administrateur système (`root`).

---

## Synthèse des commandes & Pratique (Simulateur)

Dans cette salle, nous avons interagi avec l'AttackBox et la machine de laboratoire distante via SSH pour manipuler le système de fichiers et gérer les utilisateurs
