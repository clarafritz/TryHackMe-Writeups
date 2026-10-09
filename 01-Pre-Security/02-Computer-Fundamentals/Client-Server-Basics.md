# Writeup TryHackMe : Client-Server Basics

- **Parcours :** Pre-Security
- **Date :** 09/10/2026
- **Module :** 2) Computer Fundamentals
- **Niveau :** Facile / Débutant

---

## Objectifs de la Room
Comprendre le modèle de communication client-serveur (requête/réponse). Assimiler les notions de base d'adressage réseau : IP, Ports, DNS et Protocole. Examiner la structure d'une requête HTTP GET et de la réponse associée via les Developer Tools d'un navigateur.

---

## Notions Clés

  - **Modèle Client-Serveur :** Le client (ex. un navigateur web) initie toujours la demande (requête) et le serveur traite cette demande pour renvoyer une réponse.
  - **Protocole :** Ensemble de règles et de syntaxe définissant la structure des échanges entre le client et le serveur (ex. HTTP, HTTPS).
  - **Adresse IP :** Identifiant réseau unique d'une machine (équivalent de l'adresse postale).
  - **DNS (Domain Name Service) :** Système traduisant un nom de domaine lisible par l'humain (`www.google.com`) en une adresse IP compréhensible par la machine.
  - **Port :** Point d'accès numérique identifiant un service spécifique exécuté sur un serveur (ex. port 80 pour HTTP, port 443 pour HTTPS).
  - **Composants d'une URL HTTP :**
    - *Schéma :* Le protocole utilisé (`http` ou `https`).
    - *Hôte :* Le nom de domaine ou l'adresse IP du serveur.
    - *Chemin / Fichier :* La ressource demandée (`/contact`, `index.html`).

---

## Synthèse des commandes & Pratique (Simulateur)

Dans cette salle, nous avons utilisé l'outil d'inspection réseau du navigateur Firefox (**DevTools**) sur le simulateur pour observer le trafic HTTP :
  1. **Ouverture des outils de développement :** `Touche F12` (ou Clic droit > *Inspecter*).
  2. **Onglet Réseau (Network Tab) :** Analyse des requêtes envoyées lors du rechargement de la page (`http://httpdemo.local:8080`).
  3. **Inspection d'une requête GET :**
     - **En-têtes (Headers) :** Visualisation de la méthode (`GET`), de l'hôte (`httpdemo.local`), du chemin (`/`), de l'adresse IP (`127.0.0.1:8080`) et du code de statut (`200 OK`).
     - **Corps de la réponse (Response) :** Inspection du code HTML brut renvoyé par le serveur.
