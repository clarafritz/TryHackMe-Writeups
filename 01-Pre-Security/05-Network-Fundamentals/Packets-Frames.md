# Writeup TryHackMe : Packets & Frames

- **Parcours :** Pre-Security
- **Date :** 18/10/2026
- **Module :** 5) Network Fundamentals
- **Niveau :** Facile

---

## Objectifs de la Room
Comprendre comment les données sont segmentées en plus petites unités (paquets et trames) et transmises à travers un réseau en utilisant les protocoles TCP et UDP, ainsi que le rôle des ports réseaux.

---

## Notions Clés

- **Paquets vs Trames :**
  - **Paquet :** Unité de données de la **Couche 3 (Réseau)** contenant des adresses IP (source et destination), un TTL (*Time To Live*) et un *checksum*.
  - **Trame :** Unité de données de la **Couche 2 (Liaison de données)** qui encapsule le paquet avec des adresses MAC.

- **Protocole TCP (Transmission Control Protocol) :**
  - Orienté connexion, garantit l'intégralité et l'ordre des données.
  - **Three-Way Handshake (Poignée de main en 3 temps) :**
    1. **SYN :** Le client demande la synchronisation.
    2. **SYN/ACK :** Le serveur accuse réception et demande la synchronisation.
    3. **ACK :** Le client confirme la connexion.
  - **Fermeture de connexion :** Utilise les paquets **FIN** et **ACK**.

- **Protocole UDP (User Datagram Protocol) :**
  - Protocol sans état (*stateless*), non orienté connexion.
  - Pas d'accusé de réception ni de retransmission en cas de perte de données.
  - Privilégie la vitesse et la fluidité (streaming, appels vidéo, jeux en ligne).

- **Notion de Ports (0 à 65535) :**
  - Permettent d'acheminer le trafic vers les bons services/applications sur un hôte.
  - **Ports standards (Well-Known Ports : 0 - 1023) :**
    - `21` : FTP (Transfert de fichiers)
    - `22` : SSH (Connexion sécurisée en ligne de commande)
    - `80` : HTTP (Web non chiffré)
    - `443` : HTTPS (Web chiffré)
    - `445` : SMB (Partage de fichiers/imprimantes)
    - `3389` : RDP (Bureau à distance)
