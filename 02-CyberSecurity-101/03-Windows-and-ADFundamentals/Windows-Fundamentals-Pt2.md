# Writeup TryHackMe : Windows Fundamentals 2

- **Parcours :** Cyber Security 101
- **Date :** 28/10/2026
- **Module :** 3) Windows and AD Fundamentals
- **Niveau :** Facile / Débutant

---

## Objectifs de la Room
Découvrir et maîtriser l'ensemble des utilitaires d'administration système intégrés à Microsoft Windows (`msconfig`, UAC, `compmgmt`, `msinfo32`, `resmon`, `cmd`, `regedit`)

---

## Notions Clés

- **Configuration du Système (`msconfig.exe`) :** Utilitaire central pour gérer le démarrage du système, les services d'arrière-plan et lancer d'autres outils d'administration
- **Contrôle de Compte d'Utilisateur (`UserAccountControlSettings.exe`) :** Mécanisme de sécurité réglable sur 4 niveaux qui contrôle les alertes de modification du système
- **Gestion de l'Ordinateur (`compmgmt.msc`) :** Console MMC regroupant le Planificateur de tâches, l'Observateur d'événements, les Dossiers partagés, la Gestion des disques et les Services
- **Informations Système (`msinfo32.exe`) :** Outil affichant la vue d'ensemble du matériel, des composants et de l'environnement logiciel (dont les variables d'environnement)
- **Moniteur de Ressources (`resmon.exe`) :** Outil d'analyse en temps réel pour le Processeur, la Mémoire, le Disque et le Réseau
- **Invite de Commandes (`cmd.exe`) :** Interface en ligne de commande pour interroger le système (`hostname`, `whoami`), le réseau (`ipconfig /all`, `netstat`) et les ressources réseau (`net`)
- **Éditeur du Registre (`regedit.exe`) :** Base de données hiérarchique contenant la configuration globale du système, du matériel et des applications
