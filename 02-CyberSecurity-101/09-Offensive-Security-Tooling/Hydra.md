### Writeup TryHackMe : Hydra
*   **Parcours :** Cyber Security 101
*   **Module :** 9) Offensive Security Tooling
*   **Date :** 27/11/2026
*   **Niveau :** Débutant

---

#### Objectifs de la Room
Comprendre le fonctionnement d'Hydra, un outil en ligne de commande spécialisé dans les attaques par force brute en ligne contre des services d'authentification réseau actifs, et l'appliquer sur deux vecteurs concrets : un formulaire d'authentification Web (`http-post-form`) et un serveur d'accès distant (`ssh`).

#### Notions clés
##### 1. Principes d'Hydra et options de base
*   **Brute-force en ligne (Online Brute-Force) :** attaque consistant à tester automatiquement une liste d'identifiants directement contre un service réseau actif (contrairement au cassage hors ligne de empreintes/hashes avec Hashcat ou John the Ripper).
*   **Options fondamentales :**
    *   `-l <user>` / `-L <fichier>` : spécifie un nom d'utilisateur unique ou une liste d'utilisateurs.
    *   `-p <pass>` / `-P <wordlist>` : spécifie un mot de passe unique ou un dictionnaire (ex. `rockyou.txt`).
    *   `-t <nombre>` : définit le nombre de tâches parallèles (threads) exécutées simultanément (par défaut `16`, souvent réduit à `4` sur SSH pour éviter la saturation).
    *   `-s <port>` : précise un port personnalisé si le service n'écoute pas sur son port standard.
    *   `-V` : active le mode verbeux (affiche chaque couple identifiant/mot de passe testé en temps réel).

##### 2. Attaque par force brute sur formulaire Web (`http-post-form`)
*   **Reconnaissance préalable :** inspection du code source HTML ou de l'onglet Réseau (DevTools) pour identifier le chemin de soumission (`action`), les attributs `name` des champs de saisie et le message d'erreur renvoyé en cas d'échec.
*   **Syntaxe de la chaîne cible :** `"<chemin>:<paramètres_POST>:<condition_échec>"`
    *   `^USER^` et `^PASS^` : variables dynamiques remplacées par Hydra à chaque tentative dans les paramètres POST (ex. `username=^USER^&password=^PASS^`).
    *   `F=<chaîne>` : indique la chaîne de caractères présente dans la réponse HTTP qui signale un échec d'authentification (ex. `F=Your username or password is incorrect`).
*   **Exemple de commande complète :**
    `hydra -l molly -P /usr/share/wordlists/rockyou.txt <IP_CIBLE> http-post-form "/login:username=^USER^&password=^PASS^:F=Your username or password is incorrect" -V`

##### 3. Attaque par force brute sur service SSH (`ssh`)
*   **Ciblage direct du protocole :** pas de paramètres HTML requis ; Hydra interagit directement avec le démon SSH sur le port `22`.
*   **Commande complète :**
    `hydra -l molly -P /usr/share/wordlists/rockyou.txt <IP_CIBLE> -t 4 ssh`
*   **Exploitation post-découverte :** connexion au shell distant via `ssh molly@<IP_CIBLE>` pour explorer l'arborescence utilisateur (`ls -la`) et récupérer les fichiers sensibles.
