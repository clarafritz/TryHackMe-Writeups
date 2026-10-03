# Intro to LAN - TryHackMe

- **Date :** 03/10/2026
- **Catégorie :** Réseaux & Infrastructure
- **Lien :** https://tryhackme.com/room/introtolan


## Objectif : 
  - Comprendre le fonctionnement d'un réseau local (LAN), la topologie réseau, les équipements d'interconnexion (Switch, Router) et les protocoles associés.


---------------------------------------------------------

## Notions clés 

### 1. Topologies Réseau
  - **Étoile (Star) :** Connexion individuelle à un équipement central (Switch/Hub). La plus répandue (fiable, évolutive), mais plus chère (câblage) et vulnérable à la panne du point central.
  - **Bus :** Câble principal unique. Très économique et simple, mais débit lent (partagé) et aucun secours si le câble rompt.
  - **Anneau (Ring) :** Appareils connectés en boucle ("jeton"). Circulation unidirectionnelle facilitant le dépannage, mais trafic non optimal et coupure globale en cas de panne d'un hôte.

### 2. Équipements
  - **Switch (Commutateur) :** Connecte les appareils au sein d'un même LAN via leurs adresses MAC.
  - **Routeur :** Interconnecte des réseaux différents et achemine le trafic entre eux grâce au **routage**.

### 3. Sous-réseautage (Subnetting)
  - Divise un réseau en sous-réseaux plus petits (ex. Compta, RH, Finance) pour des gains en sécurité et gestion.
  - Masque de sous-réseau : codé sur **32 bits** (ex: 4 octets de 0 à 255)
  - Éléments fondamentaux : **Adresse Réseau** (début du réseau), **Adresse Hôte** (identifiant machine), **Passerelle par défaut / Default Gateway** (routeur de sortie).

### 4. Protocoles Réseau
  - **ARP (Address Resolution Protocol) :** Associe une adresse IP (identifiant logique) à une adresse MAC (identifiant physique) en diffusant des messages *Request* / *Reply*.
  - **DHCP (Dynamic Host Configuration Protocol) :** Attribue automatiquement les adresses IP via le processus **DORA** :
      1. `Discover` (Client -> Serveur) : Le client cherche un serveur DHCP.
      2. `Offer` (Serveur -> Client) : Le serveur propose une IP.
      3. `Request` (Client -> Serveur) : Le client confirme vouloir cette IP.
      4. `ACK` (Serveur -> Client) : Le serveur valide l'attribution.
   
---------------------------------------------------------

## Synthèse des commandes & exercices

- **Simulation de topologies :** Validation du parcours des paquets de données sur les topologies Bus, Étoile et Anneau.
- **Notations et termes à retenir pour TryHackMe :**
    1. Passerelle par défaut $\rightarrow$ `default gateway`
    2. Attribution dynamique IP $\rightarrow$ Processus `DORA` (`Discover`, `Offer`, `Request`, `ACK`)
    3. Identifiants $\rightarrow$ MAC = Identifiant physique | IP = Identifiant logique
