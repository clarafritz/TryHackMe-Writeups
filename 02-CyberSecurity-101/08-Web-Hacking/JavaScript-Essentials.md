# Writeup TryHackMe : JavaScript Essentials

- **Parcours :** Cyber Security 101
- **Module :** 8) Web Hacking
- **Date :** 24/11/2026
- **Niveau :** Débutant

---

## Objectifs de la Room

Comprendre les fondamentaux du langage JavaScript, ses modes d'intégration dans une page HTML, ainsi que les principaux risques de sécurité associés côté client : abus des fonctions de dialogue, contournement de la logique de contrôle de flux, exposition de secrets en dur et analyse de code minifié ou obfusqué.

## Notions clés

### 1. Fondamentaux et exécution côté client
- **JavaScript (JS) :** langage de programmation interprété exécuté directement par le navigateur web (côté client) sans compilation préalable.
- **Variables :** conteneurs de données déclarés via `var` (portée de fonction), `let` (portée de bloc, modifiable) ou `const` (portée de bloc, constante).
- **Types de données :** `string`, `number`, `boolean`, `null`, `undefined` et `object`.
- **Fonctions et boucles :** regroupement d'instructions réutilisables (`function`) et répétition d'actions via des boucles (`for`, `while`, `do...while`).
- **Console Chrome (`Ctrl + Shift + I`) :** outil intégré aux DevTools permettant d'inspecter le DOM et d'exécuter du code JS en direct.

### 2. Intégration de JavaScript dans HTML
- **JS interne :** code placé directement dans le document HTML entre des balises `<script>...</script>` (dans `<head>` ou `<body>`).
- **JS externe :** code stocké dans un fichier séparé (`.js`) et importé dans le HTML via l'attribut `src` (`<script src="script.js"></script>`), idéal pour la réutilisation sur plusieurs pages.
- **Audit du code source (`Ctrl + U` / `View Page Source`) :** permet d'identifier immédiatement si les scripts sont embarqués en clair dans la page ou chargés depuis des fichiers externes.

### 3. Fonctions de dialogue et abus
- **`alert()` :** affiche une boîte d'avertissement avec un bouton `OK` (peut être détournée en boucle pour bloquer la navigation de l'utilisateur).
- **`prompt()` :** affiche une boîte de dialogue demandant une saisie utilisateur et retourne la chaîne entrée (ou `null` si annulé).
- **`confirm()` :** demande une validation (`OK` / `Cancel`) et retourne un booléen (`true` ou `false`).
- **Contexte offensif :** ces fonctions servent couramment de preuve de concept (PoC) pour démontrer une faille Cross-Site Scripting (XSS).

### 4. Contrôle de flux et failles d'authentification côté client
- **Instructions conditionnelles (`if-else`, `switch`) :** orientent l'exécution du programme selon qu'une condition est évaluée à `true` ou `false`.
- **Contournement côté client :** toute vérification d'identité ou de condition (`if (username === "admin" && password === "...")`) exécutée uniquement dans le navigateur est inspectable et contournable par l'utilisateur via les DevTools.

### 5. Minification, obfuscation et bonnes pratiques
- **Minification :** compression d'un fichier JS (suppression des espaces, commentaires et sauts de ligne) pour réduire sa taille et accélérer son chargement.
- **Obfuscation :** transformation volontaire du code (renommage de variables, encodage hexadécimal, code factice) pour le rendre illisible par un humain tout en conservant son exécution fonctionnelle.
- **Désobfuscation :** reconstruction d'un code JS lisible (via des outils dédiés ou la console) afin d'en analyser la logique réelle.
- **Bonnes pratiques de sécurité :** ne jamais se fier uniquement à la validation côté client (toujours valider côté serveur), ne jamais stocker de secrets en dur (clés API, mots de passe) dans le code front-end, et vérifier la fiabilité des bibliothèques tierces importées.
