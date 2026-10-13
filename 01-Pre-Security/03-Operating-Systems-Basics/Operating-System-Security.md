# Writeup TryHackMe : Operating System Security

- **Parcours :** Pre-Security
- **Date :** 13/10/2026
- **Module :** 3) Operating Systems Basics
- **Niveau :** Facile / Débutant 

---

## Objectifs de la Room
Comprendre les principes fondamentaux de la sécurité des systèmes d'exploitation (OS). Découvrir le modèle CIA (Confidentialité, Intégrité, Disponibilité), identifier les vulnérabilités courantes (mots de passe faibles, mauvaises permissions, malwares) et pratiquer une élévation de privilèges simple sous Linux via un accès SSH.

---

## Notions Clés

  - **Triangle CIA :**
    - **Confidentialité :** S'assurer que seules les personnes autorisées ont accès aux données.
    - **Intégrité :** Garantir que les données ne sont pas altérées ou modifiées sans autorisation.
    - **Disponibilité :** Veiller à ce que les systèmes et données restent accessibles quand on en a besoin.
  - **Vecteurs de vulnérabilité courants :**
    - **Authentification & Mots de passe faibles :** Utilisation de mots de passe prévisibles (ex. `123456`, motifs de clavier ou mots du dictionnaire) faciles à deviner ou à attaquer par dictionnaire.
    - **Permissions de fichiers :** Le non-respect du principe du moindre privilège permet à un utilisateur non autorisé de lire ou modifier des fichiers sensibles.
    - **Malwares :** Logiciels malveillants (Trojans, Ransomwares) ciblant l'accès au système ou le chiffrement des données contre rançon.
  - **Commandes d'exploration & d'élévation sous Linux :**
    - `ssh user@IP` : Connexion à une machine distante de manière sécurisée.
    - `whoami` : Affiche l'identifiant de l'utilisateur actif.
    - `ls` / `cat` : Lister et lire les fichiers.
    - `history` : Affiche l'historique des commandes exécutées par l'utilisateur (peut révéler des erreurs comme la saisie involontaire d'un mot de passe).
    - `su - user` : Permet de changer d'utilisateur (Switch User), par exemple basculer vers le compte privilégié `root`.

---

## Synthèse des commandes & Pratique (Simulateur)

Au cours de cet atelier pratique, nous avons simulé une attaque par devinement de mot de passe et une élévation de privilèges :
  1. **Connexion SSH initiale :**
     - Connexion au compte de Sammie via `ssh sammie@10.129.171.225` avec le mot de passe `dragon`.
     - Inspection des fichiers locaux (`ls`, `cat draft.md`).
  2. **Attaque par dictionnaire sur un autre compte :**
     - Identification de l'utilisateur `johnny`.
     - Test de connexion avec les mots de passe les plus courants jusqu'à trouver le bon mot de passe pour `johnny`.
  3. **Analyse d'erreurs et élévation de privilèges (`root`) :**
     - Exécution de `history` sous le compte de Johnny pour analyser les commandes passées.
     - Découverte du mot de passe `root` saisi par erreur dans l'historique des commandes.
     - Prise de contrôle du compte administrateur avec `su - root`.
     - Lecture du fichier final dans le répertoire `/root` pour récupérer le drapeau : `cat /root/flag.txt`.
