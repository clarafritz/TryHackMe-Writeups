### Writeup TryHackMe : Burp Suite: The Basics
*   **Parcours :** Cyber Security 101
*   **Module :** 8) Web Hacking
*   **Date :** 26/11/2026
*   **Niveau :** Débutant

---

#### Objectifs de la Room
Comprendre l'architecture et l'interface de Burp Suite Community Edition, configurer un proxy d'interception HTTP/HTTPS avec un navigateur externe (FoxyProxy + certificat CA PortSwigger) ou le navigateur intégré, isoler une cible via le périmètre (*Target Scope*) et exploiter le proxy pour contourner une validation côté client via une faille XSS par réflexion (*Reflected XSS*).

#### Notions clés
##### 1. Présentation de Burp Suite et de son interface
*   **Burp Suite :** framework écrit en Java dédié aux tests d'intrusion d'applications web et mobiles, agissant comme un proxy d'interception (*Man-in-the-Middle* local) entre le navigateur et le serveur cible.
*   **Éditions :** *Community* (gratuite, outils manuels de base : Proxy, Repeater, Decoder, Comparer, Sequencer) vs *Professional* (payante, ajoute le scanner automatique de vulnérabilités, Intruder non bridé et Burp Collaborator).
*   **Organisation de l'interface :** barre de navigation supérieure (modules principaux), sous-onglets contextuels, panneau d'inspection requête/réponse (*Pretty*, *Raw*, *Hex*, *Render*) et panneau latéral droit **Inspector** (analyse et édition rapide des en-têtes, paramètres et encodages).

##### 2. Fonctionnement du Burp Proxy et interception
*   **Principe d'interception :** le proxy écoute par défaut sur `127.0.0.1:8080`. Lorsque **Intercept is on** est actif, toute requête HTTP(S) est mise en pause avant d'atteindre le serveur, permettant de la lire, la modifier, la transférer (**Forward**) ou l'annuler (**Drop**).
*   **Journalisation passive :** même lorsque **Intercept is off** est activé, Burp enregistre silencieusement tout le trafic dans **Proxy > HTTP history** et reconstruit l'arborescence de l'application dans **Target > Site map**.
*   **Navigateurs compatibles :** configuration d'un navigateur externe (Firefox + extension **FoxyProxy** routant vers `127.0.0.1:8080`) ou utilisation directe du navigateur Chromium préconfiguré (**Open browser** dans *Proxy > Intercept*, avec option `--no-sandbox` sous Linux en tant que `root`).

##### 3. Gestion du périmètre (Target Scope) et trafic HTTPS
*   **Target Scope :** définition stricte des domaines ou adresses IP autorisés (*Target > Scope > Add*). L'activation de la règle `And | URL | Is in target scope` dans **Proxy settings** (*Request/Response interception rules*) permet d'ignorer le trafic parasite d'Internet et de ne figer que les requêtes destinées à la cible.
*   **Proxy HTTPS et certificat CA :** pour déchiffrer le trafic TLS à la volée, Burp génère dynamiquement des certificats signés par sa propre autorité de certification (**PortSwigger CA**). Il est indispensable de télécharger `cacert.der` via `http://burp/cert` et de l'importer dans les autorités de confiance du navigateur pour éviter les blocages de sécurité TLS.

##### 4. Exploitation pratique : contournement côté client et Reflected XSS
*   **Limites de la validation côté client :** les contrôles de format (ex. vérification d'adresse e-mail via JavaScript ou attributs HTML) exécutés uniquement dans le navigateur sont facilement contournables en modifiant la requête après validation.
*   **Encodage URL (`Ctrl + U`) :** lors de l'injection d'une charge utile dans une requête `POST` (`application/x-www-form-urlencoded`), les caractères spéciaux (`<`, `>`, `"`, espaces) doivent être encodés en URL dans Burp avant d'être transférés afin de ne pas casser la syntaxe de la requête HTTP.
*   **Preuve de concept (PoC) :** remplacement d'un champ valide par `<script>alert("Succ3ssful XSS")</script>` encodé en URL, suivi d'un **Forward**, déclenchant l'exécution du script dans le navigateur.
