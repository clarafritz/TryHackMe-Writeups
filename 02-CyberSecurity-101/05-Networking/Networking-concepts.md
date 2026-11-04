
# Writeup TryHackMe : Networking Concepts

- **Parcours :** Cyber Security 101
- **Date :** 04/11/2026
- **Module :** 5) Networking
- **Niveau :** Facile / Débutant

---

## Objectifs de la Room

Découvrir les fondamentaux des communications réseau à travers les modèles OSI et TCP/IP, comprendre l'adressage IPv4, les sous-réseaux et le routage, distinguer les protocoles de transport TCP et UDP, maîtriser le principe d'encapsulation des données et apprendre à établir des connexions TCP depuis un terminal avec `telnet` pour interagir avec différents services réseau.

---

## Notions Clés

- **Modèle OSI (Open Systems Interconnection) :**
  - **Rôle :** Modèle conceptuel normalisé par l'ISO permettant de décomposer les communications réseau en 7 couches, chacune remplissant une fonction spécifique
  - **Couche 7 — Application :** Fournit les services réseau aux applications. Exemples : `HTTP`, `FTP`, `DNS`, `SMTP`
  - **Couche 6 — Présentation :** Assure la représentation, l'encodage, la compression et éventuellement le chiffrement des données
  - **Couche 5 — Session :** Gère l'établissement, le maintien et la fermeture des sessions de communication
  - **Couche 4 — Transport :** Assure la communication de bout en bout entre applications, notamment grâce à `TCP`, `UDP` et aux numéros de port
  - **Couche 3 — Réseau :** Gère l'adressage logique et le routage des paquets entre différents réseaux via `IPv4`, `IPv6` et `ICMP`
  - **Couche 2 — Liaison de données :** Assure le transfert des trames sur un réseau local, notamment avec Ethernet (`802.3`) et Wi-Fi (`802.11`)
  - **Couche 1 — Physique :** Transmet les bits sous forme de signaux électriques, optiques ou radio à travers les supports physiques

- **Adresses MAC (Media Access Control) :**
  - **Identification :** Adresse de liaison généralement codée sur 48 bits (6 octets) et représentée en hexadécimal, par exemple `A4:C3:F0:85:AC:2D`
  - **Structure :** Dans une adresse MAC universelle classique, les 3 premiers octets correspondent à un identifiant de fabricant (OUI), tandis que les 3 derniers identifient l'interface
  - **Utilisation :** Permettent notamment l'acheminement des trames Ethernet au sein d'un réseau local

- **Modèle TCP/IP (Transmission Control Protocol / Internet Protocol) :**
  - **Rôle :** Architecture de protocoles utilisée pour les communications sur Internet, développée à partir des années 1970
  - **Couche Application :** Regroupe les fonctions des couches OSI 5, 6 et 7. Protocoles : `HTTP`, `HTTPS`, `FTP`, `DNS`, `SSH`, `SMTP`
  - **Couche Transport :** Correspond à la couche OSI 4 et utilise principalement `TCP` et `UDP`
  - **Couche Internet :** Correspond à la couche OSI 3 et assure l'adressage et l'acheminement des paquets via `IP` et `ICMP`
  - **Couche Liaison :** Prend en charge les communications sur le réseau directement connecté, notamment avec Ethernet et Wi-Fi
  - **Différence OSI / TCP/IP :** OSI possède 7 couches théoriques, tandis que TCP/IP est généralement représenté en 4 couches. Une représentation pédagogique à 5 couches distingue également la couche physique

- **Adressage IPv4 et Sous-réseaux :**
  - **Adresse IPv4 :** Identifiant logique de 32 bits composé de 4 octets, chacun compris entre 0 et 255. Exemple : `192.168.1.10`
  - **IPv6 :** Version du protocole IP utilisant des adresses de 128 bits pour disposer d'un espace d'adressage beaucoup plus important
  - **Sous-réseau (Subnet) :** Division logique d'un réseau IP permettant de regrouper des équipements et d'organiser l'adressage
  - **Masque de sous-réseau :** Distingue les bits correspondant au réseau de ceux correspondant aux hôtes. Exemple : `255.255.255.0`
  - **Notation CIDR :** Indique le nombre de bits du préfixe réseau. Exemple : `192.168.1.0/24`, où les 24 premiers bits identifient le réseau
  - **Adresse réseau :** Identifie le sous-réseau, par exemple `192.168.1.0/24`
  - **Adresse Broadcast :** Adresse de diffusion permettant de joindre tous les hôtes d'un sous-réseau IPv4, par exemple `192.168.1.255/24`
  - **Adresses IP privées (RFC 1918) :** Trois plages réservées aux réseaux internes : `10.0.0.0/8`, `172.16.0.0/12` et `192.168.0.0/16`
  - **Reconnaissance des adresses privées :** Une adresse commençant par `10`, par `192.168`, ou par `172` avec un deuxième octet compris entre `16` et `31`, appartient à une plage privée
  - **Adresses IP publiques :** Adresses pouvant être utilisées pour le routage sur Internet lorsqu'elles appartiennent à des plages globalement routables
  - **NAT (Network Address Translation) :** Mécanisme de traduction d'adresses permettant notamment aux machines d'un réseau privé d'accéder à Internet via une adresse publique
  - **Routage :** Acheminement des paquets entre différents réseaux grâce aux routeurs, qui utilisent les adresses IP et leurs tables de routage pour déterminer le prochain saut

- **Configuration Réseau sous Windows et Linux :**
  - **Windows :** `ipconfig` permet d'afficher les informations de configuration IP des interfaces réseau.
  - **Linux / Unix :** `ifconfig` permet de consulter ou configurer les interfaces réseau avec les outils historiques.
  - **Inspection des Adresses :** `ip address show` ou `ip a` affiche les interfaces réseau et leurs adresses IPv4/IPv6.
  - **Inspection du Routage :** `ip route` affiche la table de routage IPv4 et permet d'identifier notamment la passerelle par défaut.

- **Protocoles de Transport TCP et UDP :**
  - **UDP (User Datagram Protocol) :** Protocole sans connexion, léger et rapide, ne garantissant ni la livraison, ni l'ordre de réception des datagrammes. Utilisé notamment pour les communications temps réel, certains échanges DNS et les jeux en ligne.
  - **TCP (Transmission Control Protocol) :** Protocole orienté connexion assurant un flux de données fiable et ordonné grâce aux numéros de séquence, aux accusés de réception et aux retransmissions
  - **Différence Principale :** TCP privilégie la fiabilité et le contrôle de transmission, tandis qu'UDP minimise la surcharge protocolaire sans fournir lui-même de mécanisme de fiabilité
  - **Three-Way Handshake :** Établissement d'une connexion TCP en trois étapes : `SYN` (demande de connexion), `SYN-ACK` (acceptation et accusé de réception), puis `ACK` (confirmation)
  - **Numéros de Séquence :** Permettent à TCP de suivre les octets transmis, de remettre les données dans l'ordre et de détecter les données manquantes.
  - **Accusés de Réception :** Les indicateurs `ACK` permettent de confirmer la réception des données et de participer au mécanisme de fiabilité TCP

- **Ports Réseau :**
  - **Rôle :** Identifier les services et applications communiquant sur un hôte à travers les protocoles de transport
  - **Taille :** Numéros codés sur 16 bits, soit 65 536 valeurs possibles de `0` à `65535`, le port `0` étant réservé
  - **Ports Bien Connus :** `0–1023`, généralement associés aux services standards
  - **Ports Enregistrés :** `1024–49151`, utilisés par divers services et applications
  - **Ports Dynamiques / Éphémères :** `49152–65535`, plage définie par l'IANA, souvent utilisée pour les connexions clientes, bien que les plages effectives dépendent du système
  - **Exemples :** `21` (FTP), `22` (SSH), `25` (SMTP), `53` (DNS), `80` (HTTP), `443` (HTTPS)

- **Encapsulation et Décapsulation :**
  - **Encapsulation :** Processus par lequel chaque couche ajoute ses informations de contrôle aux données provenant de la couche supérieure afin de permettre leur transmission
  - **Données Applicatives :** Informations produites par une application, comme une requête HTTP
  - **Segment TCP / Datagramme UDP :** La couche transport ajoute un en-tête contenant notamment les ports source et destination
  - **Paquet IP :** La couche Internet ajoute un en-tête IP contenant notamment les adresses source et destination
  - **Trame Ethernet / Wi-Fi :** La couche liaison encapsule le paquet IP avec les informations nécessaires à sa transmission sur le lien local. Une trame Ethernet comporte notamment un en-tête et un champ de contrôle de fin
  - **Bits :** La couche physique transmet les informations sous forme de signaux sur le support de communication
  - **Décapsulation :** Processus inverse à la réception, permettant de retirer progressivement les informations de contrôle jusqu'à restituer les données à l'application
  - **Cycle de Vie d'un Paquet :** Les données traversent les couches réseau, sont transmises vers leur destination, éventuellement via plusieurs routeurs, puis sont décapsulées à la réception
  - **Passage par un Routeur :** Le routeur examine l'adresse IP de destination et réencapsule généralement le paquet dans une nouvelle trame adaptée au prochain lien

- **Telnet et Tests de Connectivité TCP :**
  - **Protocole Telnet :** Protocole d'accès à un terminal distant fonctionnant sur TCP, traditionnellement sur le port `23`
  - **Sécurité :** Telnet ne chiffre pas les communications. `SSH` est privilégié pour l'administration distante sécurisée
