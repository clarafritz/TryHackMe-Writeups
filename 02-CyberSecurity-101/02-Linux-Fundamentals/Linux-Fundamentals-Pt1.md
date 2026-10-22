# Writeup TryHackMe : Linux Fundamentals Pt1

- **Parcours :** Cyber Security 101
- **Date :** 22/10/2026
- **Module :** 2) Linux Fundamentals
- **Niveau :** Facile / Débutant

---

## Objectifs de la Room
S'initier à l'utilisation du système d'exploitation Linux et de son interface en ligne de commande (CLI)[cite: 14, 17]. Apprendre à interagir avec le terminal, exécuter des commandes de base pour identifier l'utilisateur courant, afficher du texte, naviguer dans l'arborescence des fichiers, lire le contenu de documents, rechercher efficacement des informations (fichiers ou texte) et manipuler les opérateurs du shell (redirections et enchaînement de commandes).

---

## Notions Clés

- **Système d'exploitation & Terminal Linux :**
  - **Importance en cybersécurité :** Linux alimente la majorité des serveurs web et des outils de sécurité. Le terminal (CLI) offre plus de rapidité, de précision et de contrôle que l'interface graphique (GUI)
  - **Commandes et sorties :** L'interaction dans le terminal repose sur des instructions textuelles saisies par l'utilisateur (commandes) auxquelles le système répond par du texte (sortie)

- **Commandes d'information & Affichage :**
  - **`whoami` :** Affiche le nom de l'utilisateur actuellement connecté sur le système.
  - **`echo` :** Génère et affiche un texte spécifié dans la sortie du terminal (les expressions comportant plusieurs mots nécessitent des guillemets)

- **Navigation & Manipulation de Fichiers :**
  - **`pwd` (*Print Working Directory*) :** Affiche le chemin absolu du répertoire de travail actuel (« Où suis-je ? »)
  - **`ls` (*List*) :** Liste le contenu (fichiers et dossiers) du répertoire courant.
  - **`cd` (*Change Directory*) :** Permet de se déplacer d'un dossier à un autre
  - **`cat` (*Concatenate*) :** Lit et affiche le contenu d'un fichier directement dans le terminal

- **Recherche Automatisée :**
  - **`find` :** Permet de localiser des fichiers sur le système par leur nom ou leurs critères (ex. `find -name "passwords.txt"`).
  - **`grep` :** Effectue une recherche de chaînes de caractères ou de motifs spécifiques à l'intérieur des fichiers (ex. `grep "THM" access.log`)

- **Opérateurs Shell & Redirections :**
  - **`&` :** Exécute la commande en arrière-plan sans attendre sa fin pour garder le terminal disponible.
  - **`&&` :** Enchaîne deux commandes en attendant que la première se termine avec succès avant de lancer la suivante
  - **`>` (Redirection d'écrasement) :** Redirige la sortie d'une commande vers un fichier en **écrasant** tout le contenu préexistant
  - **`>>` (Redirection d'ajout) :** Redirige la sortie d'une commande en l'**ajoutant** à la fin du fichier sans effacer le contenu existant

---

## Synthèse des commandes & Pratique (Simulateur)

Dans cette salle, nous avons interagi avec une machine cible Ubuntu pour exécuter des commandes de base, effectuer des recherches et utiliser les opérateurs shell :

- **Vérification d'identité et affichage :**
  ```bash
  whoami
  echo "TryHackMe"
