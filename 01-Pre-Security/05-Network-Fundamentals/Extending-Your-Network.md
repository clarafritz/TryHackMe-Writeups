# Writeup TryHackMe : Étendre votre réseau (Extending Your Network)

- **Parcours :** Pre-Security
- **Date :** 18/10/2026
- **Module :** 5) Network Fundamentals
- **Niveau :** Facile

---

## Objectifs de la Room
Découvrir les technologies et équipements permettant d'étendre les réseaux locaux (LAN) et de sécuriser/interconnecter des flux à travers Internet (Port Forwarding, Firewalls, VPN, Switchs et Routeurs).

---

## Notions Clés

- **Redirection de port (Port Forwarding) :**
  - Permet de rendre un service hébergé sur un réseau privé (ex. serveur web local) accessible depuis l'extérieur (Internet) via l'IP publique du routeur.
  - La configuration s'effectue directement au niveau du **routeur**.

- **Pare-feu (Firewall) :**
  - Équipement ou logiciel de sécurité filtrant le trafic entrant et sortant selon des règles prédéfinies (IP source/destination, ports, protocoles).
  - Intervient principalement aux **couches 3 (Réseau)** et **4 (Transport)** du modèle OSI.
  - **Types de pare-feu :**
    - **Stateful (À état) :** Inspecte l'intégralité de la connexion et garde en mémoire l'état des sessions.
    - **Stateless (Apatride) :** Inspecte chaque paquet de manière isolée sans conserver d'historique de session.

- **Réseau Privé Virtuel (VPN) :**
  - Technologie créant un tunnel chiffré au-dessus d'Internet pour interconnecter des réseaux distants ou sécuriser des hôtes.
  - **Technologies VPN :**
    - **PPP :** Chiffre et authentifie les données, mais non routable.
    - **PPTP :** Permet d'acheminer le trafic PPP sur un réseau (tunneling point à point).
    - **IPSec :** Protocole de chiffrement robuste opérant directement au niveau du protocole IP.

- **Équipements de réseau LAN :**
  - **Routeur :** Interconnecte des réseaux distincts et achemine (*route*) les paquets à la couche 3 (IP).
  - **Switch Couche 2 :** Interconnecte les hôtes d'un même réseau local en commutant les trames via les adresses MAC.
  - **Switch Couche 3 :** Combine les fonctionnalités de commutation (MAC) et de routage (IP).
  - **VLAN (Virtual LAN) :** Segmente logiquement un même commutateur physique pour isoler les flux entre différents services (ex. Ventes, Comptabilité).
