# Writeup TryHackMe : HTTP in Detail

- **Parcours :** Pre-Security
- **Date :** 18/10/2026
- **Module :** 6) How The Web Works
- **Niveau :** Facile

---

## Objectifs de la Room
Comprendre le fonctionnement complet du protocole HTTP/HTTPS, la structure des URL, le format des requêtes et réponses HTTP, les méthodes principales, les codes d'état, l'utilisation des en-têtes ainsi que le fonctionnement des cookies.

---

## Notions Clés

- **HTTP vs HTTPS :**
  - **HTTP (Hypertext Transfer Protocol) :** Protocole de communication client-serveur utilisé pour transmettre des ressources web (HTML, images, vidéos).
  - **HTTPS (Hypertext Transfer Protocol Secure) :** Version sécurisée de HTTP chiffrant le trafic via SSL/TLS, garantissant la confidentialité et l'authenticité du serveur.

- **Structure d'une URL (Uniform Resource Locator) :**
  - **Scheme :** Protocole utilisé (`http`, `https`).
  - **User Info :** Identifiants d'authentification facultatifs (`user:password@`).
  - **Host/Domain :** Nom de domaine ou adresse IP du serveur.
  - **Port :** Port de connexion (`80` pour HTTP, `443` pour HTTPS).
  - **Path :** Chemin d'accès à la ressource demandée.
  - **Query String :** Paramètres transmis dans l'URL (ex. `?id=1`).
  - **Fragment :** Ancre pointant vers une section spécifique de la page (`#section`).

- **Structure d'une transaction HTTP :**
  - **Requête :** Contient la méthode HTTP, le chemin, la version du protocole, les en-têtes (ex. `Host`, `User-Agent`, `Referer`) et un corps de message optionnel.
  - **Réponse :** Contient le code d'état HTTP, la version du protocole, les en-têtes de réponse (ex. `Content-Type`, `Content-Length`, `Server`) et le contenu demandé (HTML, JSON, etc.).

- **Méthodes HTTP principales :**
  - **GET :** Récupérer des ressources depuis le serveur.
  - **POST :** Soumettre des données au serveur (ex. création de compte, formulaires).
  - **PUT :** Mettre à jour une ressource existante sur le serveur.
  - **DELETE :** Supprimer une ressource spécifique du serveur.

- **Plages de codes d'état HTTP :**
  - **100-199 :** Réponses d'information.
  - **200-299 :** Succès (ex. `200 OK`, `201 Created`).
  - **300-399 :** Redirections (ex. `301 Moved Permanently`, `302 Found`).
  - **400-499 :** Erreurs client (ex. `400 Bad Request`, `401 Unauthorized`, `403 Forbidden`, `404 Not Found`).
  - **500-599 :** Erreurs serveur (ex. `500 Internal Server Error`, `503 Service Unavailable`).

- **En-têtes et Cookies :**
  - **En-têtes courants :** `User-Agent` (navigateur du client), `Content-Type` (type MIME), `Content-Length` (taille de la réponse), `Host` (nom de domaine demandé).
  - **Gestion de la session (Cookies) :** HTTP étant sans état (*stateless*), le serveur utilise l'en-tête `Set-Cookie` pour stocker un jeton de session sur le client. Le client le renvoie ensuite via l'en-tête `Cookie` à chaque requête ultérieure pour maintenir l'authentification.
