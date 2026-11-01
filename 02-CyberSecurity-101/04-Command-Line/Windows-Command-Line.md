# Writeup TryHackMe : Windows Command Line

- **Parcours :** Cyber Security 101
- **Date :** 01/11/2026
- **Module :** 4) Command Line
- **Niveau :** Facile / Débutant

---

## Objectifs de la Room
Maîtriser l'interpréteur de commandes par défaut de Windows (`cmd.exe`). Apprendre à interroger le système, analyser et dépanner la configuration réseau, manipuler l'arborescence des fichiers/répertoires et gérer les processus actifs en ligne de commande.

---

## Notions Clés

- **Introduction au CLI (`cmd.exe`) :**
  - **Rôle :** Interpréteur de commandes par défaut sous Windows servant à exécuter des instructions en ligne de commande sans interface graphique.
  - **Avantages :** Consommation réduite des ressources système, automatisation simple via des fichiers batch (`.bat`), exécution rapide et gestion à distance efficace (notamment via SSH).

- **Informations Système de Base :**
  - **Identification du Système :** `ver` affiche la version exacte de l'OS, tandis que `systeminfo` fournit des détails complets (nom d'hôte, fabricant, processeur, mémoire, hotfixes).
  - **Pilotes & Environnement :** `driverquery` liste les pilotes installés et `set` affiche les variables d'environnement (dont la variable `PATH`).
  - **Pagination & Utilitaire :** L'option `| more` permet de lire la sortie page par page, `help` (ou `/?`) affiche l'aide des commandes et `cls` efface la console.

- **Dépannage Réseau :**
  - **Configuration IP :** `ipconfig` affiche la configuration réseau de base, tandis que `ipconfig /all` détaille l'adresse physique (MAC), le serveur DHCP et les serveurs DNS.
  - **Analyse & Connectivité :** `ping` teste la joignabilité d'un hôte via ICMP, `tracert` trace les sauts de routeurs et `nslookup` effectue des requêtes DNS.
  - **Connexions & Ports :** `netstat` liste les connexions actives. La combinaison `netstat -abon` permet de visualiser les ports d'écoute (`-a`), les exécutables associés (`-b`), les identifiants PID (`-o`) et les adresses sous forme numérique (`-n`).
  - **Service RPC :** Le service `RpcSs` (`svchost.exe`) écoute sur le port **135**.

- **Gestion des Fichiers et des Disques :**
  - **Navigation & Arborescence :** `cd` affiche ou change de répertoire (`cd ..` pour remonter), `dir` liste le contenu des dossiers (`/a` pour les fichiers cachés, `/s` pour les sous-dossiers), et `tree` affiche une vue graphique de l'arborescence.
  - **Opérations sur Répertoires & Fichiers :** `mkdir` crée un dossier et `rmdir` le supprime. La lecture se fait avec `type` ou `more`, les déplacements/copies avec `move` et `copy`, et la suppression avec `del` ou `erase`. Le caractère générique `*` permet de cibler plusieurs fichiers.

- **Gestion des Tâches et des Processus :**
  - **Lister les Processus :** `tasklist` affiche l'ensemble des tâches en cours d'exécution avec leur nom d'image et leur PID.
  - **Filtrage des Tâches :** L'option `/FI` permet de cibler un processus spécifique (ex: `tasklist /FI "imagename eq notepad.exe"`).
  - **Terminer un Processus :** `taskkill /PID <PID>` permet de forcer l'arrêt d'un processus via son identifiant.

- **Maintenance & Alimentation Système :**
  - **Outils de Diagnostic :** `chkdsk` analyse l'état du disque et `sfc /scannow` vérifie/répare les fichiers système corrompus.
  - **Gestion de l'Arrêt :** `shutdown /s` éteint le système, `shutdown /r` permet de redémarrer le système et `shutdown /a` annule un arrêt ou redémarrage programmé.
