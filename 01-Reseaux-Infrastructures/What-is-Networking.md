# What is Networking ? - TryHackMe

- **Date :** 02/10/2026
- **Catégorie :** Réseaux & Infrastructure
- **Lien :** https://tryhackme.com/room/whatisnetworking


## Objectif : 
  - Comprendre les bases des réseaux informatiques, des adresses IP et de la communication entre machines. 


---------------------------------------------------------

## Notions clés 

### 1. Qu'est-ce qu'un réseau & Internet ?
  - **Réseau (Network) :** Ensemble d'au moins 2 équipements interconnectés qui communiquent entre eux
  - **Internet :** Réseau global reliant une multitude de réseaux privés et publics
      A) Origines :
          - Issu d'ARPANET (fin des années 1960), utilisé pour le secteur militaire DARPA
          - 1989 : Démocratisé par Tim Berners-Lee avec la création du World Wide Web (www)
   
### 2. Identification des équipements
Toute machine sur un réseau possède deux identifiants majeurs :
  - **Adresse IP (Internet Protocol) :** Identifiant logique/temporaire, divisé en 4 octets (ex: `192.168.1.1`) -> L'identifiant vulnérable
      - **IP Privée :** Utilisée au sein du réseau local
      - **IP Publique :** Utilisée pour identifier le réseau sur Internet
  - **Adresse MAC (Media Access Control) :** Identifiant physique/unique gravé en usine sur la carte réseau (12 caractères hexadécimaux, ex: `a4:c3:f0:85:ac:2d`)
      - **MAC Spoofing :** Usurpation de l'adresse MAC pour contourner des restrictions d'accès (ex : wifi payant dans un hôtel)
  - **IPv4 vs IPv6 :** L'IPv4 ($2^{32}$ adresses) est complétée par l'IPv6 ($2^{128}$ adresses) pour pallier la pénurie d'adresses

### 3. Outils de diagnostic
  - **Command ICMP (Internet Control Message Protocol) :** ('ping') Permet de tester la connectivité et la latence entre deux machines via le protocole ICMP.
      Syntaxe : `ping <IP_ou_nom_domaine>`.


---------------------------------------------------------
## Synthèse des commandes & exercices
1) Diagnostic de connectivité : `ping 10.10.10.10`
2) Manipulation pratique : Simulation de MAC spoofing pour accéder au réseau Wi-Fi d'un hôtel
