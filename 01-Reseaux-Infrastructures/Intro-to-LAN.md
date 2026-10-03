# Intro to LAN - TryHackMe

- **Date :** 03/10/2026
- **Catégorie :** Réseaux & Infrastructure
- **Lien :** https://tryhackme.com/room/introtolan


## Objectif : 
  - Comprendre le fonctionnement d'un réseau local (LAN), la topologie réseau, les équipements d'interconnexion (Switch, Router) et les protocoles associés.


---------------------------------------------------------

## Notions clés 

### 1. Topologies Réseau
  - **Étoile (Star) :** Appareils reliés à un équipement central (Switch/Hub). Très évolutive mais point de défaillance unique au centre.
  - **Bus :** Câble unique partagé. Économique mais sujet aux collisions et goulots d'étranglement.
  - **Anneau (Ring) :** Données circulant en boucle. Moins de goulots d'étranglement mais une coupure interrompt tout le réseau.

### 2. Équipements
  - **Switch (Commutateur) :** Connecte les appareils au sein d'un même LAN via leurs adresses MAC.
  - **Router (Routeur) :** Interconnecte différents réseaux et achemine le trafic entre eux (Routage)

### 3. Sous-réseautage (Subnetting)
  - Divise un réseau global en sous-réseaux plus petits (efficacité, sécurité, gestion)
  - Masque de sous-réseau : codé sur **32 bits** (ex: 4 octets de 0 à 255)
  - Éléments clés : **Adresse Réseau**, **Adresse Hôte**, **Passerelle par défaut (Default Gateway)**

### 4. Protocoles Réseau
  - **ARP (Address Resolution Protocol) :** Associe une adresse IP (identifiant logique) à une adresse MAC (identifiant physique) en diffusant des messages *Request* / *Reply*.
  - **DHCP (Dynamic Host Configuration Protocol) :** Attribue automatiquement des adresses IP via le processus **DORA** :
      1. `Discover` (Client -> Serveur)
      2. `Offer` (Serveur -> Client)
      3. `Request` (Client -> Serveur)
      4. `ACK` (Serveur -> Client)
   
  
