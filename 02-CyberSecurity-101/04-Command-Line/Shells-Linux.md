# Writeup TryHackMe : Linux Shells

- **Parcours :** Cyber Security 101
- **Date :** 02/11/2026
- **Module :** 4) Command Line
- **Niveau :** Facile / Débutant

---

## Objectifs de la Room
Découvrir le fonctionnement des interpréteurs de commandes Linux (shells), maîtriser les commandes de navigation et de manipulation de fichiers/répertoires, comprendre les spécificités des différents shells (`Bash`, `Fish`, `Zsh`) et s'initier aux bases du scripting shell (variables, boucles, conditions, permissions et analyse de logs).

---

## Notions Clés

- **Introduction au CLI & Shell :**
  - **Rôle :** Le shell fait office d'intermédiaire entre l'utilisateur et le noyau du système d'exploitation Linux, permettant d'exécuter des instructions en ligne de commande (CLI).
  - **Avantages :** Consommation réduite des ressources système, automatisation puissante des tâches d'administration et précision des commandes par rapport à une interface graphique (GUI).

- **Navigation et Manipulation de Fichiers :**
  - **Recherche & Inspection :** `pwd` affiche le répertoire de travail actuel, `cd` permet de changer de dossier et `ls` liste le contenu des répertoires.
  - **Lecture & Filtrage :** `cat` affiche l'intégralité d'un fichier texte et `grep` permet de filtrer et rechercher des motifs spécifiques au sein de fichiers volumineux.

- **Types de Shells Linux :**
  - **Identification & Configuration :** `echo $SHELL` affiche le shell actif de la session, `cat /etc/shells` recense tous les interpréteurs installés sur le système et `chsh` permet de modifier le shell par défaut.
  - **Bourne Again Shell (`Bash`) :** Shell standard et le plus répandu sous Linux. Il ne possède pas de coloration syntaxique native ni de correction orthographique automatique par défaut.
  - **Friendly Interactive Shell (`Fish`) :** Shell axé sur la convivialité, proposant la coloration syntaxique et les suggestions de commandes intégrées de manière native.
  - **Z Shell (`Zsh`) :** Shell moderne combinant les fonctionnalités de Bash et Fish, proposant la correction orthographique et une grande personnalisation via des frameworks
  - **Historique :** La commande `history` liste l'ensemble des commandes précédemment saisies au cours de la session active.

- **Scripting Shell et Composants :**
  - **En-tête & Shebang :** La première ligne d'un script doit contenir le shebang (`#!/bin/bash`) pour indiquer au système l'interpréteur exact à utiliser lors de l'exécution.
  - **Permissions & Exécution :** La commande `chmod +x script.sh` accorde les droits d'exécution au fichier script, qui peut ensuite être lancé avec la syntaxe `./script.sh`.
  - **Variables & Saisie :** Déclaration de variables (`nom="valeur"`) et récupération des saisies utilisateur via la commande `read`.
  - **Structure d'un Script :** Utilisation de boucles (`loops` avec `for` et `while`) pour gérer l'itération des tâches, d'instructions conditionnelles (`if`, `elif`, `else`, `fi`) pour la prise de décision logique et de commentaires (`#`) pour documenter le code.

- **Analyse de Logs et Automatisation :**
  - **Élévation de Privilèges :** Utilisation de `sudo su` pour passer en utilisateur superutilisateur (`root`) afin d'accéder aux fichiers système restreints.
  - **Inspection des Journaux :** Automatisation du traitement et du filtrage des fichiers de journalisation (`/var/log/`) via des scripts shell pour rechercher rapidement des motifs ou des secrets spécifiques (ex: `authentication.log`).
