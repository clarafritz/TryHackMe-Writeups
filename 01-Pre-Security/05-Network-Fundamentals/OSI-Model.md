# Writeup TryHackMe : Modèle OSI (OSI Model)

- **Parcours :** Pre-Security
- **Date :** 17/10/2026
- **Module :** 5) Network Fundamentals
- **Niveau :** Facile

---

## Objectifs de la Room
Comprendre la structure, les mécanismes et l'importance du modèle OSI (*Open Systems Interconnection*), un cadre théorique en 7 couches qui régit la communication entre équipements réseaux hétérogènes.

---

## Notions Clés

  - **Vue d'ensemble du modèle OSI :**
    - **Définition :** Modèle théorique en 7 couches standardisant la communication réseau.
    - **Encapsulation :** Processus d'ajout d'en-têtes (*headers*) spécifiques à chaque couche descendue lors de l'envoi de données.

  - **Détail des 7 Couches :**
    - **Couche 7 — Application :** Interface directe avec l'utilisateur et les logiciels (navigateurs, clients FTP/e-mail). Protocole exemple : DNS, HTTP, FTP.
    - **Couche 6 — Présentation :** Traduction, formatage, compression et chiffrement des données (ex. SSL/TLS, HTTPS).
    - **Couche 5 — Session :** Gestion (ouverture, maintien, fermeture) et synchronisation des connexions entre applications distantes.
    - **Couche 4 — Transport :** Acheminement et gestion du flux de données end-to-end.
      - **TCP (Transmission Control Protocol) :** Orienté connexion, fiable, garantit la réception et l'ordre des données (contrôle d'erreurs).
      - **UDP (User Datagram Protocol) :** Non orienté connexion, rapide, sans garantie de livraison (utilisé pour le streaming, le jeu vidéo, DNS).
    - **Couche 3 — Réseau :** Routage des paquets à travers différents réseaux via des adresses logiques (adresses IP). Exexmples de protocoles de routage : OSPF, RIP.
    - **Couche 2 — Liaison de données :** Communication physique directe entre hôtes d'un même réseau via des adresses physiques (adresses MAC) gravées sur les cartes réseau (NIC).
    - **Couche 1 — Physique :** Transmission brute des bits (1 et 0) sous forme de signaux électriques, optiques ou radio sur les supports physiques (câbles Ethernet, fibre optique, Wi-Fi).
