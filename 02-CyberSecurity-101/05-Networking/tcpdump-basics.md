
# Writeup TryHackMe : TCPdump - The Basics

- **Parcours :** Cyber Security 101
- **Date :** 10/11/2026
- **Module :** 5) Networking
- **Niveau :** Facile / Débutant

---

## Objectifs de la Room

Découvrir TCPdump, un outil d'analyse réseau en ligne de commande, et apprendre à capturer, enregistrer, filtrer et examiner les paquets réseau dans des fichiers PCAP.

---

## Notions Clés

- **TCPdump :**
  - Analyseur de paquets réseau en ligne de commande.
  - Utilise la bibliothèque `libpcap` pour la capture.
  - Complémentaire à Wireshark pour l'analyse des fichiers PCAP.

- **Capture et lecture :**
  - `-i` → Sélectionner une interface réseau.
  - `-w` → Enregistrer les paquets dans un fichier PCAP.
  - `-r` → Lire un fichier PCAP.
  - `-c` → Limiter le nombre de paquets.
  - `-n` / `-nn` → Désactiver la résolution des noms.
  - `-v` / `-vv` / `-vvv` → Augmenter les détails affichés.

- **Expressions de filtrage :**
  - `host IP` → Filtrer une adresse IP.
  - `src host IP` / `dst host IP` → Filtrer par source ou destination.
  - `port N` → Filtrer un port.
  - `tcp`, `udp`, `icmp`, `arp` → Filtrer par protocole.
  - `and`, `or`, `not` → Combiner les conditions.

- **Filtrage avancé :**
  - `greater N` / `less N` → Filtrer selon la taille des paquets.
  - `tcp[tcpflags]` → Examiner les indicateurs TCP.
  - `tcp-syn`, `tcp-ack`, `tcp-fin`, `tcp-rst` → Identifier les flags TCP.
  - `&` → Tester la présence d'un flag.
  - `==` → Vérifier une correspondance exacte.

- **Affichage des paquets :**
  - `-q` → Affichage simplifié.
  - `-e` → Afficher l'en-tête Ethernet et les adresses MAC.
  - `-A` → Afficher les données en ASCII.
  - `-xx` → Afficher les données en hexadécimal avec l'en-tête de liaison.
  - `-X` → Afficher les données en hexadécimal et ASCII.

- **Analyse pratique :**
  - Identifier les requêtes ARP et leurs émetteurs.
  - Examiner les requêtes DNS et les noms de domaine recherchés.
  - Compter les paquets correspondant à un filtre avec `wc -l`.
  - Analyser les indicateurs TCP et la taille des paquets.



