# Writeup TryHackMe : Linux Fundamentals Pt3

- **Parcours :** Cyber Security 101
- **Date :** 25/10/2026
- **Module :** 2) Linux Fundamentals
- **Niveau :** Facile / Débutant

---

## Objectifs de la Room
Approfondir l'utilisation du système d'exploitation Linux en maîtrisant les utilitaires essentiels du quotidien. Découvrir l'édition de texte en terminal (Nano, Vim), les méthodes de transfert et de partage de fichiers (Wget, SCP, serveur web Python), la gestion des processus et des services (`ps aux`, `top`, `kill`, `systemctl`), l'automatisation des tâches avec Cron (`crontab`), la gestion des paquets logiciels (`apt`) ainsi que la consultation des journaux système (`/var/log`).

---

## Notions Clés

- **Éditeurs de Texte en Terminal :**
  - **Nano :** Éditeur simple et intuitif, idéal pour créer ou modifier un fichier texte directement dans la console.
  - **Vim :** Éditeur avancé et puissant fonctionnant par modes (insertion, commande), largement utilisé par les développeurs et administrateurs.

- **Transfert & Partage de Fichiers :**
  - **`wget` :** Permet de télécharger des fichiers directement depuis le web via les protocoles HTTP/HTTPS.
  - **`scp` (*Secure Copy*) :** Transfert de manière sécurisée et chiffrée des fichiers entre deux machines réseau via SSH.
  - **Serveur HTTP Python :** Permet de transformer instantanément un répertoire local en serveur web pour distribuer des fichiers à d'autres hôtes (`python3 -m http.server 8000`).

- **Gestion des Processus & Services :**
  - **`ps aux` :** Affiche un instantané complet de tous les processus en cours d'exécution sur le système.
  - **`top` :** Affiche en temps réel l'utilisation du processeur, de la mémoire et la liste active des processus.
  - **`kill` :** Envoie des signaux de fin de processus (ex. `SIGTERM`, `SIGKILL`) ciblés par leur identifiant (PID).
  - **`systemctl` :** Interagit avec le gestionnaire de services `systemd` (PID 1) pour démarrer, arrêter ou activer des services.
  - **Gestion Arrière-plan / Premier plan :** Basculement d'une commande en arrière-plan (`&` ou `Ctrl + Z`) et retour au premier plan (`fg`).

- **Automatisation des Tâches (Cron) :**
  - **`crontab` :** Fichier de configuration permettant de planifier l'exécution automatique de commandes ou scripts.
  - **Syntaxe Cron :** Repose sur 5 champs temporels (`MIN HEURE DOM MON DOW`) ou des mots-clés spéciaux comme `@reboot` pour lancer des actions au démarrage du système.

- **Gestion des Paquets & Dépôts (`apt`) :**
  - **Gestionnaire APT :** Permet d'installer, mettre à jour et supprimer des paquets logiciels sur Debian/Ubuntu.
  - **Sources & Clés GPG :** Les dépôts sont référencés dans `/etc/apt/sources.list` et `/etc/apt/sources.list.d/`. L'authenticité des paquets est garantie par l'ajout de clés GPG publiques (`apt-key`).

- **Journaux Système (Logs) :**
  - **`/var/log` :** Répertoire centralisant les fichiers de journalisation des applications et du système (ex. Apache, SSH, Fail2ban, UFW).
  - **Analyse d'accès web :** Consultation des fichiers `access.log` pour tracer les adresses IP clientes et les ressources web demandées.

---

## Synthèse des commandes & Pratique (Simulateur)

Dans cette salle, nous sommes intervenus en connexion SSH sur la machine cible (`10.128.147.19`) pour manipuler les processus, analyser l'automatisation et inspecter les journaux d'accès :

- **Édition de fichier avec Nano :**
  ```bash
  nano task3

- Lancement d'un serveur web HTTP rapide :
  ```bash
  python3 -m http.server 8000

- Identification d'un processus masqué :
  ```bash
  ps aux | grep THM

- Gestion d'un service système :
  ```bash
  systemctl stop myservice
  systemctl enable myservice

- Consultation de la planification Cron :
  ```bash
  crontab -l
