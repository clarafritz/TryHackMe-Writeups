
# Writeup TryHackMe : Nmap - The Basics

- **Parcours :** Cyber Security 101
- **Date :** 11/11/2026
- **Module :** 5) Networking
- **Niveau :** Facile / Débutant

---

## Objectifs de la Room

Découvrir Nmap, un outil de reconnaissance réseau permettant d'identifier les hôtes actifs, les ports ouverts, les services et leurs versions.Apprendre à configurer les scans, contrôler leur vitesse et enregistrer les résultats.

---

## Notions Clés

### 1. Découverte des hôtes

- `nmap -sn IP/24` : détecte les hôtes actifs sans scanner leurs ports.
- `nmap -sL IP/24` : liste les cibles sans les scanner.
- **Réseau local :** découverte principalement via ARP.
- **Réseau distant :** découverte via différentes sondes ICMP et TCP.

### 2. Analyse des ports

- `nmap -sT IP` : TCP Connect Scan, établit une connexion TCP complète.
- `nmap -sS IP` : TCP SYN Scan, sans terminer la connexion TCP.
- `nmap -sU IP` : scan des ports UDP.
- `nmap -F IP` : scan rapide des 100 ports les plus courants.
- `nmap -p 80,443 IP` : scan de ports spécifiques.
- `nmap -p- IP` : scan de tous les ports TCP.

**États des ports :**
- `open` : un service accepte les connexions.
- `closed` : le port est accessible, mais aucun service n'écoute.
- `filtered` : un filtrage empêche de déterminer son état.

### 3. Détection des services et du système

- `nmap -sV IP` : identifie les services et leurs versions.
- `nmap -O IP` : tente d'identifier le système d'exploitation.
- `nmap -A IP` : active plusieurs analyses avancées.
- `nmap -Pn IP` : ignore la découverte préalable des hôtes.

### 4. Vitesse et temporisation

- `-T0` à `-T5` : définit le niveau de temporisation.
- `-T3` : mode normal.
- `-T4` : mode agressif, généralement plus rapide.
- `--min-rate N` / `--max-rate N` : contrôle le débit des paquets.
- `--min-parallelism N` / `--max-parallelism N` : contrôle le parallélisme.
- `--host-timeout 5m` : limite la durée d'analyse d'un hôte.

### 5. Affichage et exportation

- `-v` : affichage détaillé.
- `-vv` : affichage encore plus détaillé.
- `-d` : informations de débogage.
- `-oN fichier.txt` : rapport texte.
- `-oX fichier.xml` : rapport XML.
- `-oG fichier.gnmap` : format exploitable avec grep.
- `-oA rapport` : exportation dans les trois formats.
