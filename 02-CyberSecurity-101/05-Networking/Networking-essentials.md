
# Writeup TryHackMe : Networking Essentials

- **Parcours :** Cyber Security 101
- **Date :** 05/11/2026
- **Module :** 5) Networking
- **Niveau :** Facile / Débutant

---

## Objectifs de la Room

Comprendre les protocoles fondamentaux des réseaux informatiques : configuration automatique avec DHCP, résolution d'adresses avec ARP, diagnostic réseau avec ICMP, Ping et Traceroute, routage des paquets et partage d'une adresse IP publique grâce au NAT/PAT.

---

## Notions Clés

- **DHCP (Dynamic Host Configuration Protocol) :**
  - Attribue automatiquement une adresse IP, un masque de sous-réseau, une passerelle et un serveur DNS.
  - Fonctionne selon les quatre étapes **DORA** : Discover → Offer → Request → Acknowledge.
  - Utilise UDP, ports `67` (serveur) et `68` (client).

- **ARP (Address Resolution Protocol) :**
  - Permet de retrouver l'adresse MAC correspondant à une adresse IPv4 sur le réseau local.
  - **ARP Request :** Requête généralement envoyée en broadcast (`ff:ff:ff:ff:ff:ff`).
  - **ARP Reply :** Réponse généralement envoyée en unicast avec l'adresse MAC recherchée.
  - Les associations IP/MAC sont temporairement conservées dans le cache ARP.

- **ICMP, Ping et Traceroute :**
  - **ICMP :** Protocole de diagnostic et de signalement des erreurs réseau.
  - **Ping :** Teste l'accessibilité d'une machine et mesure le temps aller-retour (RTT).
  - **Echo Request :** ICMP type `8` ; **Echo Reply :** ICMP type `0`.
  - **Traceroute :** Identifie les routeurs intermédiaires grâce à des sondes avec un TTL croissant.
  - **TTL (Time To Live) :** Diminue à chaque routeur traversé. À zéro, le paquet est abandonné et un message ICMP Time Exceeded (type `11`) peut être envoyé.

- **Routage et Équipements Réseau :**
  - **Switch (Couche 2) :** Relie les équipements d'un LAN et transmet les trames selon les adresses MAC.
  - **Routeur (Couche 3) :** Interconnecte plusieurs réseaux IP et achemine les paquets.
  - **Table de routage :** Permet de sélectionner le chemin vers un réseau de destination.
  - **OSPF :** Calcule les chemins à partir de la topologie réseau.
  - **EIGRP :** Protocole historiquement propriétaire Cisco.
  - **BGP :** Assure l'échange des routes entre réseaux sur Internet.
  - **RIP :** Utilise le nombre de sauts pour choisir une route.

- **NAT et PAT :**
  - **NAT (Network Address Translation) :** Traduit les adresses IP, notamment pour permettre l'accès à Internet depuis un réseau privé.
  - **PAT (Port Address Translation) :** Permet à plusieurs appareils de partager une même IP publique grâce à des ports différents.
  - **Table NAT/PAT :** Conserve les correspondances entre connexions internes et externes.
  - **Ports TCP/UDP :** Codés sur 16 bits, soit 65 536 valeurs possibles (`0` à `65535`).
