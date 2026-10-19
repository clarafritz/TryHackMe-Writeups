# Writeup TryHackMe : Putting It All Together

- **Parcours :** Pre-Security
- **Date :** 19/10/2026
- **Module :** 6) How The Web Works
- **Niveau :** Facile

---

## Objectifs de la Room
Comprendre la chaîne globale d'interactions lorsqu'un utilisateur accède à un site web, de la résolution DNS à l'affichage final, en passant par les composants d'infrastructures clés (répartiteurs de charge, CDN, WAF, bases de données) et le fonctionnement interne des serveurs web.

---

## Notions Clés

- **Chaîne d'accès complète à un site Web :**
  1. **Saisie de l'URL :** L'utilisateur entre l'adresse dans son navigateur.
  2. **Résolution DNS :** Le système vérifie le cache local puis interroge les serveurs DNS (récursifs et autoritairess) pour obtenir l'adresse IP associée au domaine.
  3. **Connexion & Sécurité :** Une connexion TCP/TLS s'établit avec le serveur (port 80 pour HTTP, 443 pour HTTPS).
  4. **Filtrage (WAF) & Répartition (Load Balancer) :** Le WAF vérifie la légitimité de la requête, puis l'équilibreur de charge la redirige vers un serveur web disponible.
  5. **Traitement Serveur :** Le serveur web génère la réponse (via des langages backend comme PHP/Python et des requêtes en base de données si nécessaire).
  6. **Rendu Client :** Le navigateur reçoit le HTML, CSS et JS (souvent accéléré par un CDN pour les fichiers statiques) et affiche la page à l'utilisateur.

- **Composants d'Infrastructures Web :**
  - **Équilibreur de charge (Load Balancer) :** Distribue le trafic entre plusieurs serveurs (via des algorithmes comme le *Round-Robin* ou la répartition pondérée) et effectue des contrôles d'intégrité (*health checks*) pour garantir la haute disponibilité.
  - **CDN (Content Delivery Network) :** Réseau de serveurs distribués géographiquement qui héberge et sert les fichiers statiques (images, CSS, JS) au plus près de l'utilisateur pour accélérer le chargement.
  - **WAF (Web Application Firewall) :** Pare-feu applicatif qui analyse et filtre le trafic HTTP/HTTPS entrant pour bloquer les attaques courantes (DoS, injections, bots) avant qu'elles n'atteignent le serveur web.
  - **Base de données :** Système de stockage persistant (MySQL, PostgreSQL, MongoDB, etc.) interrogé par le serveur web backend pour gérer les données dynamiques.

- **Fonctionnement d'un Serveur Web :**
  - **Logiciels principaux :** Apache, Nginx, IIS, NodeJS.
  - **Hôtes virtuels (Virtual Hosts) :** Permettent d'héberger plusieurs sites web distincts sur une même machine physique/IP en se basant sur l'en-tête `Host` transmis dans la requête HTTP.
  - **Contenu Statique vs Dynamique :** 
    - *Statique :* Fichiers délivrés tels quels par le serveur (HTML, CSS, JS, images).
    - *Dynamique :* Contenu généré côté serveur au moment de la requête (via du code PHP, Python, etc.). Le client ne voit jamais le code source backend, seulement le résultat HTML généré.
