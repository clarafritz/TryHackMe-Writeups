# Writeup TryHackMe : Inside a Computer System

- **Parcours :** Pre-Security
- **Date :** 09/10/2026
- **Module :** 2) Computer Fundamentals
- **Niveau :** Facile / Débutant

---

## Objectifs de la Room
- Comprendre l'architecture matérielle de base d'un système informatique (*hardware*), identifier les rôles respectifs de chaque composant interne (CPU, RAM, Stockage, Carte Mère, Alimentation) et appréhender le processus de démarrage d'un ordinateur (*Boot Process / UEFI / POST*).

---

## Notions Clés

### 1. Composants Matériels (Hardware)
  - **CPU (Central Processing Unit) :** Cerveau de l'ordinateur qui exécute les instructions des programmes et effectue les calculs.
  - **RAM (Random Access Memory) :** Mémoire vive volatile stockant temporairement les données en cours d'utilisation par le CPU pour un accès ultrarapide.
  - **Stockage (SSD / HDD) :** Mémoire non-volatile conservant les données et le système d'exploitation de manière permanente.
  - **Carte Mère - MOBO (Motherboard) :** Circuit principal qui interconnecte et fait communiquer tous les composants.
  - **PSU (Power Supply Unit) :** Bloc d'alimentation convertissant le courant électrique pour alimenter la carte mère et les composants.
  - **GPU (Graphics Processing Unit) :** Processeur dédié au traitement graphique et aux calculs parallèles.

### 2. Séquence de Démarrage (Boot Process)
  1. **Alimentation (Power-On) :** Mise sous tension de la carte mère par le bloc d'alimentation.
  2. **Firmware / UEFI :** Initialisation du micrologiciel matériel de la carte mère.
  3. **POST (Power-On Self Test) :** Test de diagnostic automatique vérifiant le bon fonctionnement des composants matériels.
  4. **Sélection du Boot Device :** Recherche du disque contenant le système d'exploitation selon la priorité configurée.
  5. **Bootloader :** Chargement du noyau du système d'exploitation (Windows, Linux) en mémoire RAM.

---

## Synthèse des commandes

*Aucune commande requise pour cette salle théorique.*
