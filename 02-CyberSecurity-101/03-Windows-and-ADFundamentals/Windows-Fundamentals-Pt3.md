# Writeup TryHackMe : Windows Fundamentals Pt3

- **Parcours :** Cyber Security 101
- **Date :** 29/10/2026
- **Module :** 3) Windows and AD Fundamentals
- **Niveau :** Facile / Débutant

---

## Objectifs de la Room
Comprendre les mécanismes et utilitaires de sécurité natifs intégrés au système d'exploitation Microsoft Windows (`Windows Update`, `Windows Security`, `Defender Firewall`, `SmartScreen`, `TPM`, `BitLocker` et `VSS`)

---

## Notions Clés

- **Mises à Jour Windows (`Windows Update`) :**
  - **Rôle :** Service responsable du déploiement des correctifs de sécurité, des mises à jour de fonctionnalités et des définitions d'antivirus.
  - **Patch Tuesday :** Publication régulière des correctifs le deuxième mardi de chaque mois par Microsoft

- **Sécurité Windows (`Windows Security`) :**
  - **Rôle :** Console centralisée regroupant l'ensemble des modules de protection du système
  - **Indicateurs d'État :** Icône verte (système protégé), jaune (recommandation), rouge (action immédiate requise)

- **Protection contre les virus et les menaces (`Virus & threat protection`) :**
  - **Protection en temps réel (*Real-time protection*) :** Analyse continue des fichiers et processus exécutés sur la machine
  - **Options d'Analyse :** Propose des analyses rapides, complètes ou personnalisées, ainsi que l'isolation en quarantaine des menaces

- **Pare-feu et protection du réseau (`Firewall & network protection`) :**
  - **Profils Réseau :**
    - **Domaine (*Domain network*) :** S'applique aux réseaux d'entreprise gérés par un contrôleur de domaine (AD)
    - **Privé (*Private network*) :** S'applique aux réseaux de confiance (domicile, bureau)
    - **Public (*Public network*) :** Profil par défaut pour les réseaux ouverts ou non sécurisés (aéroports, cafés)

- **Contrôle de l'application et du navigateur (`App & browser control`) :**
  - **Microsoft Defender SmartScreen :** Protège contre le hameçonnage et l'exécution d'applications non reconnues ou malveillantes
  - **Exploit Protection :** Intègre des protections mémoire de bas niveau (DEP, ASLR, CFG) contre l'exploitation de vulnérabilités

- **Sécurité des appareils & Hardware (`Device security`) :**
  - **TPM (*Trusted Platform Module*) :** Puce cryptographique matérielle intégrée à la carte mère fournissant des fonctions de sécurité avancées et le stockage sécurisé des clés
  - **BitLocker :** Fonctionnalité de chiffrement intégral de disque dur, s'appuyant de préférence sur la puce TPM (ou sur une clé de démarrage externe `startup key` en l'absence de TPM)

- **Service de copie instantanée de volume (`VSS - Volume Shadow Copy Service`) :**
  - **Rôle :** Service coordonnant la création de clichés instantanés (*shadow copies*) du système pour créer des points de restauration
  - **Impact en Cybersécurité :** Les malwares (notamment les rançongiciels) cherchent souvent à supprimer les clichés VSS pour empêcher la récupération des données
