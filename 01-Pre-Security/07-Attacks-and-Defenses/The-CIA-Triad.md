# Writeup TryHackMe : The CIA Triad

- **Parcours :** Pre-Security
- **Date :** 19/10/2026
- **Module :** 7) Attacks and Defenses
- **Niveau :** Facile

---

## Objectifs de la Room
Comprendre le modèle fondamental de la triade CIA (Confidentialité, Intégrité, Disponibilité), son rôle dans l'évaluation des risques et la gestion des incidents de sécurité, ainsi que son application pratique pour analyser divers scénarios d'attaques et de défenses.

---

## Notions Clés

- **Confidentialité (Confidentiality) :**
  - **Définition :** Garantit que les données sensibles et les systèmes ne sont accessibles qu'aux personnes ou processus dûment autorisés
  - **Exemples d'atteintes :** Vol d'identifiants sur un Wi-Fi public non sécurisé, fuite de données personnelles ou de documents confidentiels sur Internet
  - **Mécanismes de protection :** Chiffrement des données, contrôle d'accès strict (IAM), authentification forte, gestion des autorisations

- **Intégrité (Integrity) :**
  - **Définition :** Garantit que les informations ne sont pas modifiées, altérées ou supprimées de manière non autorisée ou accidentelle
  - **Exemples d'atteintes :** Altération d'un virement bancaire lors de son transit, modification de notes d'examen ou de prix d'articles avant le paiement
  - **Mécanismes de protection :** Fonctions de hachage (MD5, SHA-256), signatures numériques, contrôles de version, journaux d'audit (*audit logs*)
- **Disponibilité (Availability) :**
  - **Définition :** Garantit que les données, applications et services restent accessibles aux utilisateurs autorisés en temps voulu et en cas de besoin
  - **Exemples d'atteintes :** Attaque par déni de service (DDoS) rendant un site web incalculable, pannes matérielles, coupures d'électricité, ransomwares bloquant l'accès aux fichiers
  - **Mécanismes de protection :** Redondance des serveurs, répartiteurs de charge (Load Balancers), plans de continuité d'activité (PCA/PRA), sauvegardes récurrentes

- **L'état d'esprit sécuritaire (Security Mindset) :**
  - La triade CIA est un modèle cadre utilisé par les professionnels de la cybersécurité pour catégoriser les menaces, évaluer la sévérité d'un incident et concevoir une stratégie de défense équilibrée
