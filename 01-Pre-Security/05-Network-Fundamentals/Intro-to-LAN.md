# Writeup TryHackMe : Intro to LAN

- **Parcours :** Pre-Security
- **Date :** 17/10/2026
- **Module :** 5) Network Fundamentals
- **Niveau :** Facile

---

## Objectifs de la Room
Comprendre le fonctionnement et l'architecture d'un réseau local (LAN), analyser les différentes topologies de réseau, appréhender les bases du sous-réseautage (*subnetting*) ainsi que le rôle des protocoles clés de niveau réseau et liaison (ARP et DHCP).

---

## Notions Clés

  - **Topologies de Réseau Local (LAN) :**
    - **Topologie en étoile :** Les périphériques sont connectés à un équipement central (commutateur/switch). Très évolutive et fiable, bien que le composant central constitue un point de défaillance unique.
    - **Topologie en bus :** Repose sur un câble principal unique. Économique mais sujette à la saturation et aux pannes en cas de coupure du câble.
    - **Topologie en anneau :** Les appareils sont reliés en boucle. Le trafic circule dans un seul sens, ce qui évite les collisions mais rend le réseau vulnérable si un nœud tombe en panne.
    - **Équipements d'interconnexion :**
      - **Switch (Commutateur) :** Interconnecte des appareils sur un même LAN en orientant intelligemment le trafic grâce aux adresses MAC.
      - **Routeur :** Interconnecte différents réseaux entre eux et achemine les paquets d'un réseau à un autre (*routing*).

  - **Introduction au Sous-réseautage (Subnetting) :**
    - Consiste à diviser un réseau global en plusieurs sous-réseaux plus petits pour améliorer la sécurité et la gestion du trafic.
    - Repose sur un masque de sous-réseau (32 bits, divisé en 4 octets de 0 à 255).
    - Permet d'identifier :
      - **L'adresse réseau :** Identifie le début du réseau (ex. `192.168.1.0`).
      - **L'adresse de l'hôte :** Identifie un appareil spécifique dans le réseau (ex. `192.168.1.100`).
      - **La passerelle par défaut (Default Gateway) :** Adresse du routeur permettant de sortir du réseau local (ex. `192.168.1.254`).

  - **Protocoles Essentiels :**
    - **ARP (Address Resolution Protocol) :** Associe une adresse IP (identifiant logique) à une adresse MAC (identifiant physique) sur le réseau local. Fonctionne par requêtes en diffusion (*ARP Request*) et réponses unicast (*ARP Reply*).
    - **DHCP (Dynamic Host Configuration Protocol) :** Attribue automatiquement les adresses IP aux appareils.
      - **Processus DORA :**
        1. `DHCP Discover` (l'hôte cherche un serveur DHCP)
        2. `DHCP Offer` (le serveur propose une IP)
        3. `DHCP Request` (l'hôte demande l'attribution de l'IP)
        4. `DHCP ACK` (le serveur confirme la réservation)
