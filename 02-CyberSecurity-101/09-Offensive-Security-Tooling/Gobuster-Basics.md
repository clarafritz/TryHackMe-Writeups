### Writeup TryHackMe : Gobuster: The Basics
-   **Parcours :** Cyber Security 101
-   **Module :** 9) Offensive Security Tooling
-   **Date :** 28/11/2026
-   **Niveau :** Débutant

---

#### Objectifs de la Room
Comprendre le fonctionnement de Gobuster, un outil en ligne de commande écrit en Go spécialisé dans l'énumération active et le brute-force de ressources web et DNS, et l'appliquer sur trois vecteurs principaux : les répertoires et fichiers (`dir`), les sous-domaines DNS (`dns`) et les hôtes virtuels (`vhost`).

#### Notions clés
##### 1. Principes de Gobuster et options transverses
-   **Énumération par dictionnaire :** Gobuster automatise l'envoi de requêtes en combinant une cible avec chaque entrée d'une wordlist afin de découvrir des ressources cachées ou non référencées.
-   **Options fondamentales communes :**
  -   `-w <wordlist>` : spécifie le chemin vers la liste de mots utilisée pour les itérations.
  -   `-t <nombre>` : définit le nombre de threads parallèles exécutés simultanément (`10` par défaut, souvent augmenté à `64` pour accélérer les scans).
  -   `--delay <durée>` : ajoute un temps d'attente entre les requêtes pour contourner les mécanismes de détection ou de limitation de débit.
  -   `-o <fichier>` : sauvegarde les résultats de l'énumération dans un fichier de sortie.

##### 2. Énumération de répertoires et fichiers (`dir`)
-   **Fonctionnement :** ajoute chaque entrée de la wordlist à la fin de l'URL cible (`-u`) et analyse les codes d'état HTTP retournés (`200`, `301`, `403`, etc.). Gobuster n'effectue pas d'énumération récursive par défaut : chaque sous-répertoire découvert doit être scanné séparément.
-   **Options spécifiques clés :**
  -   `-u <URL>` : définit l'URL de base ciblée (avec le protocole `http://` ou `https://`).
  -   `-x <extensions>` : recherche des fichiers portant des extensions précises en complément des répertoires (ex. `-x .php,.js`).
  -   `-k` / `--no-tls-validation` : désactive la vérification des certificats TLS/SSL (indispensable face aux certificats auto-signés).
  -   `-r` / `--followredirect` : suit automatiquement les redirections HTTP (`301`/`302`).
-   **Exemple de syntaxe générique :**
    `gobuster dir -u "http://<CIBLE>" -w <WORDLIST> -x .php,.js -t 64`

##### 3. Énumération de sous-domaines (`dns`)
-   **Fonctionnement :** interroge directement les services de résolution DNS pour identifier des sous-domaines valides en préfixant le domaine cible avec les entrées de la wordlist (`<mot>.<domaine>`).
-   **Options spécifiques clés :**
  -   `-d <domaine>` / `--domain` : définit le nom de domaine racine à énumérer.
  -   `-r <serveur>` / `--resolver` : permet de spécifier un serveur DNS personnalisé pour la résolution.
  -   `-i` / `--show-ips` : affiche les adresses IP associées aux sous-domaines découverts.
-   **Exemple de syntaxe générique :**
    `gobuster dns -d <DOMAINE> -w <WORDLIST> -t 64`

##### 4. Énumération d'hôtes virtuels (`vhost`)
-   **Différence fondamentale avec `dns` :** contrairement au mode `dns`, le mode `vhost` n'interroge pas un résolveur DNS. Il envoie des requêtes HTTP directement vers l'adresse IP du serveur web en modifiant dynamiquement l'en-tête HTTP `Host:` afin de révéler des sites ou applications internes hébergés sur la même machine sans enregistrement DNS public.
-   **Options spécifiques clés :**
  -   `-u "http://<IP_CIBLE>"` : cible directement l'adresse IP du serveur web hébergeant les hôtes virtuels.
  -   `--domain <domaine>` : définit le domaine de base utilisé pour construire l'en-tête `Host:`.
  -   `--append-domain` : accole automatiquement le domaine configuré à chaque mot de la wordlist (`<mot>.<domaine>`).
  -   `--exclude-length <taille>` : élimine les faux positifs en ignorant les réponses HTTP dont la taille du corps correspond à la page par défaut du serveur (accepte une valeur unique, une liste séparée par des virgules ou une plage `min-max`).
-   **Exemple de syntaxe générique :**
    `gobuster vhost -u "http://<IP_CIBLE>" --domain <DOMAINE> --append-domain -w <WORDLIST> --exclude-length <TAILLE> -t 64`
