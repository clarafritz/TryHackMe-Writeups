
# Writeup TryHackMe : Networking Core Protocols

**Parcours :** Cyber Security 101  
**Module :** 5) Networking  
**Date :** 06/11/2026  
**Difficulté :** Facile

---

## Objectifs de la Room

Comprendre les principaux protocoles applicatifs TCP/IP, identifier leurs rôles et leurs ports. Manipuler des services réseau depuis un terminal. Observer les échanges client/serveur.

--- 

## Notions Clés

### 1. DNS & WHOIS

- **DNS (Domain Name System)** : associe notamment un nom de domaine à une adresse IP.
  - `A` : IPv4
  - `AAAA` : IPv6
  - `CNAME` : alias vers un autre nom de domaine
  - `MX` : serveur de messagerie
  - Port : **53 UDP/TCP**

- **WHOIS** : consulte les informations d'enregistrement d'un domaine (registrar, création, expiration).

```bash
nslookup example.com
nslookup -type=MX example.com
whois example.com
```

### 2. HTTP / HTTPS

- **HTTP** : échange de ressources entre navigateur et serveur.
- **HTTPS** : HTTP sécurisé avec TLS.
- Ports habituels : **80 / 443**
- Méthodes :
  - `GET` : récupérer une ressource
  - `POST` : envoyer des données
  - `PUT` : créer/remplacer une ressource
  - `DELETE` : supprimer une ressource

Exemple de requête HTTP :

```http
GET / HTTP/1.1
Host: example.com
```

### 3. FTP (File Transfer Protocol)

- Transfert de fichiers entre client et serveur.
- Port de commande : **TCP 21**
- Connexion distincte pour les données.
- Commandes :
  - `USER` / `PASS` : authentification
  - `LIST` : lister les fichiers
  - `RETR` : télécharger
  - `STOR` : envoyer

```bash
ftp <IP>
ls
get fichier.txt
bye
cat fichier.txt
```

### 4. SMTP (Simple Mail Transfer Protocol)

- Protocole d'envoi et de transfert d'e-mails.
- Ports TCP : **25**, **587**, **465** (TLS).
- Commandes :
  - `HELO` / `EHLO` : initialiser la session
  - `MAIL FROM` : expéditeur
  - `RCPT TO` : destinataire
  - `DATA` : début du contenu
  - `.` : fin du message
  - `QUIT` : déconnexion

### 5. POP3 (Post Office Protocol v3)

- Récupération des e-mails depuis un serveur.
- Ports TCP : **110 / 995** (TLS).
- Commandes :
  - `USER` / `PASS` : authentification
  - `STAT` : nombre de messages
  - `LIST` : liste des messages
  - `RETR` : récupérer un message
  - `DELE` : marquer pour suppression

### 6. IMAP (Internet Message Access Protocol)

- Consultation et synchronisation des e-mails entre plusieurs appareils.
- Ports TCP : **143 / 993** (TLS).
- Commandes :
  - `LOGIN` : authentification
  - `SELECT` : sélectionner une boîte
  - `FETCH` : récupérer un message
  - `MOVE` / `COPY` : déplacer/copier
  - `LOGOUT` : déconnexion

**Différence :** SMTP envoie, POP3 récupère, IMAP synchronise.

### 7. Manipulations réseau

- `telnet <IP> <PORT>` : ouvrir une connexion TCP vers un service.
- `nslookup` : interroger le DNS.
- `whois` : consulter l'enregistrement d'un domaine.
- `ftp` : transférer des fichiers.
- Wireshark : analyser les échanges et suivre un flux TCP/HTTP.

