# Writeup TryHackMe : Active Directory Basics

* **Parcours :** Cyber Security 101 
* **Date :** 30/10/2026
* **Module :** 3) Windows and AD Fundamentals
* **Niveau :** Débutant / Intermédiaire

---

## Objectifs de la Room

Comprendre l'architecture et les composants fondamentaux d'un domaine Active Directory (AD) sous Windows Server. Apprendre à gérer les objets (utilisateurs, ordinateurs, groupes, unités organisationnelles) via l'interface graphique (`dsa.msc`), à déléguer des privilèges, à déployer des politiques de groupe (GPO) via `gpmc.msc`, et à assimiler les mécanismes d'authentification réseau (Kerberos et NetNTLM) ainsi que les structures multi-domaines (arbres, forêts, relations de confiance).

---

## Notions Clés

- **Composants & Structure d'Active Directory :**
  - **Domaine & Contrôleur de Domaine (DC) :** Le domaine est la frontière de sécurité principale ; le DC sert d'autorité centrale pour authentifier les utilisateurs et appliquer les politiques.
  - **Security Principals & Comptes Machines :** Tous les objets AD (utilisateurs, groupes, machines) possèdent des identifiants uniques (SID). Le nom de compte d'un ordinateur joint au domaine se termine obligatoirement par un symbole `$` (ex: `TOM-PC$`).
  - **Unités Organisationnelles (UO / OU) :** Conteneurs de classement logique (par département/service) servant principalement à cibler le déploiement des stratégies de groupe (GPO). Un objet ne peut appartenir qu'à une seule UO à la fois.
  - **Groupes de Sécurité :** Ensembles d'utilisateurs ou de machines utilisés pour attribuer des autorisations d'accès. Le groupe *Domain Admins* détient les privilèges suprêmes sur le domaine.

- **Gestion des Utilisateurs & Délégation :**
  - **Protection contre la suppression accidentelle :** Activée par défaut sur les UO. Nécessite d'activer les *Advanced Features* dans `dsa.msc` pour décocher la protection dans l'onglet *Object*.
  - **Délégation de contrôle (*Delegation*) :** Pratique consistant à accorder des privilèges spécifiques (ex: réinitialisation de mots de passe) à un utilisateur non-admin sur une UO donnée sans lui donner les droits d'administrateur complets (principe du moindre privilège).

- **Gestion des Ordinateurs & Politiques de Groupe (GPO) :**
  - **Tri des Machines :** Les ordinateurs rejoignent par défaut le conteneur `Computers` et doivent être triés dans des UO distinctes (*Workstations*, *Servers*) pour appliquer des règles de sécurité adaptées à leur rôle.
  - **GPO (Group Policy Objects) :** Ensembles de configurations système/utilisateur gérés via `gpmc.msc`. Les GPO sont créées puis liées (*linked*) aux UO ou au domaine.
  - **Stockage & Synchronisation :** Les GPO sont répliquées via le partage réseau `SYSVOL` (`C:\Windows\SYSVOL\sysvol`). La commande `gpupdate /force` permet de forcer leur application immédiate sur une machine.

- **Protocoles d'Authentification :**
  - **Kerberos :** Protocole moderne et sécurisé par défaut reposant sur des tickets émis par le KDC (*Key Distribution Center*, hébergé sur le DC). Processus : Obtention d'un TGT (*Ticket Granting Ticket*) auprès du KDC, puis demande d'un TGS (*Ticket Granting Service*) pour accéder à un service spécifique (identifié par son SPN).
  - **NetNTLM :** Protocole hérité reposant sur un mécanisme de Défi/Réponse (*Challenge-Response*) en 3 étapes. Le mot de passe (ou son hachage) n'est jamais transmis directement sur le réseau.

- **Arbres, Forêts & Relations de Confiance :**
  - **Arbre (*Tree*) :** Regroupement de domaines partageant le même espace de noms continu (ex: `thm.local`, `uk.thm.local`).
  - **Forêt (*Forest*) :** Ensemble d'arbres de domaines ayant des espaces de noms différents mais partageant un schéma et un catalogue global communs.
  - **Relations de confiance (*Trusts*) :** Mécanisme permettant d'autoriser des utilisateurs d'un domaine A à accéder aux ressources d'un domaine B.

