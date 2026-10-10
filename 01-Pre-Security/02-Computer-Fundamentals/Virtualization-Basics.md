# Writeup TryHackMe : Virtualization Basics

- **Parcours :** Pre-Security
- **Date :** 10/10/2026
- **Module :** 2) Computer Fundamentals
- **Niveau :** Facile / Débutant

---

## Objectifs de la Room
Comprendre la nécessité de la virtualisation pour optimiser l'utilisation du matériel informatique. Distinguer les architectures d'hyperviseurs (Type 1 et Type 2) ainsi que les conteneurs (ex. Docker). S'entraîner à la gestion administrative de machines virtuelles et d'hôtes physiques via un outil de supervision dédié.

---

## Notions Clés

  - **Virtualisation :** Technologie permettant de diviser un serveur physique unique en plusieurs machines virtuelles indépendantes partageant les mêmes ressources matérielles.
  - **Hyperviseur :** Composant logiciel/micrologiciel jouant le rôle de gestionnaire entre le matériel physique et les environnements virtuels.
    - *Type 1 (Bare-Metal) :* S'exécute directement sur le matériel (ex. serveurs de production, datacenters).
    - *Type 2 (Hosted) :* S'exécute au-dessus d'un système d'exploitation hôte classique (ex. VirtualBox, VMware Workstation).
  - **Machine Virtuelle (VM) :** Système informatique emulé disposant de son propre OS, processeur virtuel, mémoire RAM et stockage.
  - **Conteneur :** Environnement léger et isolé qui partage le noyau du système d'exploitation hôte pour exécuter une application et ses dépendances.

---

## Synthèse des commandes & Pratique (Simulateur)

Dans cette salle, nous avons utilisé l'interface de gestion **Virtualization Manager** pour administrer une infrastructure virtualisée :
  1. **Analyse d'états de VM :**
     - Identification de la VM `Mail-SERVER` en état d'erreur.
     - Redémarrage du service via le bouton dédié (reprise de l'état `Running`).
  2. **Création et déploiement de VM :**
     - Configuration et allocation de ressources pour `Marketing-VM` (4 vCPU, 8 Go RAM, 100 Go Disque).
  3. **Supervision des hôtes physiques (Host Monitoring) :**
     - Analyse de la charge CPU, RAM et stockage des serveurs physiques (`HV-PROD-01`, `HV-PROD-02`, `HV-BACKUP-01`).
     - Identification du serveur sous forte charge (`HV-PROD-02`) hébergeant le plus grand nombre de machines virtuelles (8 VMs).
