# Writeup TryHackMe : What is Networking?

- **Parcours :** Pre-Security
- **Date :** 15/10/2026
- **Module :** 5) Network Fundamentals
- **Niveau :** Facile

---

## Objectifs de la Room
Comprendre les principes fondamentaux du réseau informatique, la structure globale d'Internet, les méthodes d'identification des périphériques (adresses IP et MAC) ainsi que l'utilisation de la commande de diagnostic `ping`.

---

## Notions Clés

  - **Qu'est-ce qu'un réseau ?**
    - Un réseau informatique est un ensemble d'appareils (ordinateurs, serveurs, téléphones) interconnectés pour échanger des données.
    - **Internet** est un « réseau de réseaux », interconnectant des réseaux privés et publics à l'échelle mondiale.

  - **Identification des Périphériques :**
    - **Adresse IP (Internet Protocol) :** Identifiant logique modifiable attribué à un hôte sur un réseau.
      - **IPv4 :** Composée de 4 octets (ex. `192.168.1.1`), chacun variant de 0 à 255.
      - **IPv6 :** Conçue pour pallier la pénurie d'adresses IPv4, elle utilise des adresses de 128 bits écrites en hexadécimal.
      - **IP Publique vs Privée :** Une IP privée identifie un appareil au sein d'un réseau local (ex. réseau domestique), tandis qu'une IP publique identifie ce réseau sur Internet.
    - **Adresse MAC (Media Access Control) :** Adresse physique unique (12 caractères hexadécimaux) gravée sur la carte réseau par le fabricant.
      - Les 6 premiers caractères identifient le fabricant (OUI).
      - Les 6 derniers constituent un numéro de série unique.
      - L'adresse MAC peut être usurpée (*spoofing*) pour contourner des filtres de sécurité basés sur le contrôle d'accès MAC.

  - **Commandes de Diagnostic :**
    - **Ping :** Utilise le protocole **ICMP** (*Internet Control Message Protocol*) pour mesurer la connectivité et la latence entre deux hôtes grâce à l'envoi de paquets d'écho (`Echo Request` / `Echo Reply`).
    - Syntaxe de base : `ping <IP_ou_Domaine>` (ex. `ping 8.8.8.8`).
