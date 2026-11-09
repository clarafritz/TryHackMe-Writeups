
# Writeup TryHackMe : Wireshark - The Basics

- **Parcours :** Cyber Security 101
- **Date :** 09/11/2026
- **Module :** 5) Networking
- **Niveau :** Facile / Débutant

---

## Objectifs de la Room

Découvrir Wireshark et son interface, apprendre à analyser les paquets réseau dans des fichiers PCAP, naviguer dans une capture, rechercher des informations, extraire des fichiers et utiliser les filtres d'affichage pour isoler et examiner les communications réseau.

---

## Notions Clés

- **Wireshark :**
  - **Rôle :** Analyseur de paquets réseau open source permettant de capturer et d'inspecter le trafic.
  - **Utilisation :** Diagnostic réseau, analyse de protocoles et investigation de sécurité.
  - **Limite :** Wireshark n'est pas un IDS ; il analyse le trafic sans bloquer les attaques.

- **Fichiers PCAP / PCAPNG :**
  - **PCAP :** Format permettant d'enregistrer des paquets réseau.
  - **PCAPNG :** Format enrichi pouvant contenir des métadonnées, des commentaires et des informations sur les interfaces.
  - **Propriétés :** `Statistics → Capture File Properties` permet de consulter les informations d'une capture.
  - **SHA256 :** Empreinte cryptographique de 256 bits utilisée pour vérifier l'intégrité d'un fichier.
  - **Fusion :** `File → Merge` permet de regrouper plusieurs captures.

- **Interface Wireshark :**
  - **Packet List :** Liste des paquets avec numéro, heure, IP source/destination, protocole et taille.
  - **Packet Details :** Décomposition du paquet selon les protocoles et couches réseau.
  - **Packet Bytes :** Affichage des octets en hexadécimal et ASCII.
  - **Coloring Rules :** Coloration des paquets selon des règles permettant de repérer rapidement certains événements.

- **Analyse des paquets :**
  - **Frame :** Taille, horodatage et informations générales du paquet.
  - **Ethernet II :** Adresses MAC source et destination (couche 2).
  - **IPv4 :** Adresses IP et TTL (couche 3).
  - **TCP / UDP :** Ports et informations de transport (couche 4).
  - **HTTP :** Requêtes, réponses et données applicatives (couche 7).
  - **TTL :** Compteur décrémenté par les routeurs, limitant la durée de vie d'un paquet IP.
  - **TCP Payload :** Données transportées dans un segment TCP.

- **Navigation et recherche :**
  - **`Ctrl + G` :** Aller directement à un numéro de paquet.
  - **`Ctrl + F` :** Rechercher une chaîne, une valeur hexadécimale ou un champ.
  - **`Ctrl + M` :** Marquer temporairement un paquet.
  - **Packet Comments :** Ajouter ou consulter des commentaires sur un paquet.
  - **Export Specified Packets :** Exporter une sélection de paquets.
  - **Export Packet Bytes :** Extraire les octets sélectionnés d'un paquet.
  - **Export Objects :** Extraire certains fichiers transférés via des protocoles pris en charge.
  - **Time Display Format :** Modifier le format des horodatages.

- **Informations pour experts :**
  - **Accès :** `Analyze → Expert Information`.
  - **Chat :** Informations générales.
  - **Note :** Événements notables.
  - **Warning :** Avertissements concernant des anomalies potentielles.
  - **Error :** Erreurs détectées, notamment des paquets malformés.
  - **Attention :** Une alerte Wireshark ne signifie pas automatiquement une attaque.

- **Filtres Wireshark :**
  - **Capture Filter :** Sélectionne les paquets enregistrés pendant la capture.
  - **Display Filter :** Masque les paquets ne correspondant pas au filtre, sans les supprimer.
  - **Apply as Filter :** Applique immédiatement un filtre à partir d'un champ.
  - **Prepare as Filter :** Prépare un filtre sans l'appliquer.
  - **Conversation Filter :** Isole les paquets d'une conversation réseau.
  - **Colorize Conversation :** Met en couleur une conversation sans masquer les autres.
  - **Apply as Column :** Ajoute un champ comme colonne dans la liste des paquets.

- **Exemples de filtres d'affichage :**
  - `http` → Trafic HTTP.
  - `tcp` → Trafic TCP.
  - `dns` → Trafic DNS.
  - `ip.addr == 192.168.1.10` → Paquets liés à cette adresse IP.
  - `tcp.port == 80` → Paquets utilisant le port TCP 80.
  - `tcp.stream eq 0` → Paquets appartenant à une conversation TCP spécifique.

- **Follow Stream :**
  - **Rôle :** Reconstituer les échanges d'une conversation réseau.
  - **Accès :** `Analyze → Follow → TCP/UDP/HTTP Stream`.
  - **Utilité :** Examiner les requêtes et réponses, retrouver des informations applicatives et comprendre une communication.
  - **Limite :** Les données chiffrées restent illisibles sans les secrets nécessaires au déchiffrement.
