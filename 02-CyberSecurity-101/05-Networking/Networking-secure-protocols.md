
# Writeup TryHackMe : Networking Secure Protocols

- **Parcours :** Cyber Security 101
- **Date :** 08/11/2026
- **Module :** 5) Networking
- **Niveau :** Facile / Débutant

---

## Objectifs de la Room

Comprendre comment sécuriser les communications réseau grâce à TLS, SSH et VPN, découvrir les protocoles applicatifs sécurisés et apprendre à analyser du trafic HTTPS chiffré avec Wireshark.

---

## Notions Clés

- **SSL / TLS (Secure Sockets Layer / Transport Layer Security) :**
  - **SSL :** Ancien protocole de sécurité, aujourd'hui remplacé par TLS
  - **TLS :** Protocole permettant de sécuriser les communications entre un client et un serveur
  - **Confidentialité :** Chiffre les données pour empêcher leur lecture
  - **Intégrité :** Protège contre les modifications non détectées
  - **Authentification :** Permet notamment de vérifier l'identité du serveur
  - **TLS 1.3 :** Version moderne du protocole TLS

- **Certificats TLS :**
  - **Certificat Numérique :** Associe une identité à une clé publique
  - **CA (Certificate Authority) :** Autorité chargée de signer les certificats
  - **CSR :** Demande de signature d'un certificat
  - **Let's Encrypt :** Autorité proposant des certificats TLS gratuits
  - **Certificat Auto-signé :** Certificat signé par son propriétaire, sans validation par une autorité tierce reconnue

- **HTTP / HTTPS :**
  - **HTTP :** Protocole web non chiffré utilisant généralement `TCP 80`
  - **HTTPS :** HTTP sécurisé par TLS utilisant généralement `TCP 443`
  - **Connexion HTTPS :** Établissement TCP → Négociation TLS → Échanges HTTP chiffrés
  - **Wireshark :** HTTP est lisible en clair, contrairement au contenu HTTPS sans les secrets de déchiffrement

- **Protocoles Mail Sécurisés :**
  - **SMTP :** Envoi d'e-mails — `TCP 25`
  - **SMTP avec TLS :** `TCP 465` (TLS implicite) ou `TCP 587` (STARTTLS)
  - **POP3 :** Récupération d'e-mails — `TCP 110`
  - **POP3S :** POP3 sécurisé par TLS — `TCP 995`
  - **IMAP :** Synchronisation des e-mails — `TCP 143`
  - **IMAPS :** IMAP sécurisé par TLS — `TCP 993`
  - **STARTTLS :** Permet de passer d'une connexion en clair à une connexion chiffrée

- **SSH (Secure Shell) :**
  - **Rôle :** Administrer une machine distante de manière sécurisée
  - **Port :** `TCP 22`
  - **OpenSSH :** Implémentation open source de SSH
  - **Sécurité :** Chiffrement, intégrité et authentification par mot de passe ou clé publique
  - **Différence avec Telnet :** Telnet (`TCP 23`) transmet les données en clair
  - **Connexion :** `ssh utilisateur@IP`
  - **Transfert X11 :** `ssh -X utilisateur@IP` permet d'utiliser certaines applications graphiques distantes
  - **Tunneling :** Permet de faire transiter des communications dans un tunnel SSH sécurisé

- **SFTP / FTPS :**
  - **SFTP :** Transfert sécurisé de fichiers via SSH — `TCP 22`
  - **FTPS :** FTP sécurisé grâce à TLS — généralement `TCP 21` ou `TCP 990`
  - **Différence :** SFTP repose sur SSH, FTPS repose sur FTP et TLS
  - **Commandes SFTP :**
    - `sftp utilisateur@IP` → Se connecter
    - `ls` → Lister les fichiers distants
    - `get fichier.txt` → Télécharger un fichier
    - `put fichier.txt` → Envoyer un fichier

- **VPN (Virtual Private Network) :**
  - **Rôle :** Créer un tunnel sécurisé à travers Internet
  - **Site-to-Site :** Relie deux réseaux distants, par exemple deux agences
  - **Remote Access :** Permet à un utilisateur distant d'accéder à un réseau privé
  - **Full Tunnel :** Tout le trafic concerné passe par le VPN
  - **Split Tunneling :** Seule une partie du trafic passe par le VPN
  - **Limite :** Un VPN ne garantit pas l'anonymat complet

- **Analyse HTTPS avec Wireshark :**
  - **Capture :** `randy-chromium.pcapng` contient le trafic réseau enregistré
  - **Secrets TLS :** `ssl-key.log` contient les secrets permettant de déchiffrer les sessions correspondantes
  - **Configuration :** `Preferences → Protocols → TLS → (Pre)-Master-Secret log filename`
  - **Filtre TLS :** `tls` → Afficher les paquets TLS
  - **Filtre HTTP/2 :** `http2` → Afficher les échanges HTTP/2 décodés
  - **Filtre POST :** `http2.headers.method == "POST"` → Rechercher les requêtes POST
  - **Follow HTTP/2 Stream :** Examiner les échanges d'un flux HTTP/2
  - **HEADERS :** Contiennent les informations de la requête ou de la réponse
  - **DATA :** Contiennent les données applicatives échangées
  - **Multiplexage :** Plusieurs flux HTTP/2 peuvent partager une même connexion TCP
