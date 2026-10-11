# Writeup TryHackMe : Cloud Computing Fundamentals

- **Parcours :** Pre-Security
- **Date :** 11/10/2026
- **Module :** 2) Computer Fundamentals
- **Niveau :** Facile / Débutant

---

## Objectifs de la Room
Comprendre les concepts fondamentaux du Cloud Computing et son évolution depuis les serveurs physiques traditionnels. Identifier les différents modèles de service (IaaS, PaaS, SaaS) et types de déploiements (public, privé, hybride). Manipuler une console Cloud simulée (type AWS EC2) pour déployer, administrer et gérer les coûts d'instances virtuelles.

---

## Notions Clés

  - **Cloud Computing :** Accès à la demande, via Internet, à des ressources informatiques (calcul, stockage, réseau) hébergées sur une infrastructure partagée.
  - **Modèles de Service :**
    - *IaaS (Infrastructure as a Service) :* Location de composants informatiques de base (ex. machines virtuelles AWS EC2, stockage, réseau). L'utilisateur gère l'OS et les applications.
    - *PaaS (Platform as a Service) :* Fourniture d'un environnement prêt à l'emploi. L'utilisateur gère le code/application sans se soucier de l'infrastructure ou de l'OS.
    - *SaaS (Software as a Service) :* Applications clés en main accessibles via navigateur web (ex. Gmail, Zoom).
  - **Types de Déploiement :**
    - *Cloud Public :* Infrastructure mutualisée accessible via Internet (ex. AWS, Azure, GCP).
    - *Cloud Privé :* Infrastructure dédiée exclusivement à une seule organisation.
    - *Cloud Hybride :* Combinaison d'infrastructures publiques et privées communiquant entre elles.
  - **Avantages Clés :** Scalabilité (élasticité), paiement à l'usage, haute disponibilité et déploiement mondial instantané.

---

## Synthèse des commandes & Pratique (Simulateur)

Dans cette salle, nous avons utilisé l'interface **Cloud Virtual Machines Console (EC2)** pour gérer un environnement virtuel :
  1. **Déploiement d'instances EC2 :**
     - Création d'une instance `application-interface` de type `t3.micro` en état `running`.
     - Création de deux instances d'entraînement (`study-machine-1` et `study-machine-2`) de type `m5.large`.
  2. **Analyse de facturation (Billing Analysis) :**
     - Évaluation du coût global de l'infrastructure complète (170 crédits/mois).
     - Détermination du coût unitaire des instances (`m5.large` à 70 crédits/mois, `t3.micro` à 10 crédits/mois).
  3. **Optimisation des coûts :**
     - Arrêt des instances inutilisées (`study-machine-1` et `study-machine-2`), réduisant le coût estimé à 30 crédits/mois.
