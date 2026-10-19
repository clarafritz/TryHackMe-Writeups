# Writeup TryHackMe : How Websites Work

- **Parcours :** Pre-Security
- **Date :** 19/10/2026
- **Module :** 6) How The Web Works
- **Niveau :** Facile

---

## Objectifs de la Room
Comprendre la structure globale d'un site web (Front-end vs Back-end), le rôle de HTML et JavaScript dans le rendu et l'interactivité, ainsi que les risques élémentaires de sécurité liés au code côté client (exposition de données sensibles et injection HTML).

---

## Notions Clés

- **Architecture Web de base :**
  - **Front-end (Côté client) :** Ce qui est exécuté et rendu directement par le navigateur de l'utilisateur (HTML, CSS, JavaScript).
  - **Back-end (Côté serveur) :** Le serveur qui traite les requêtes HTTP, applique la logique applicative et communique avec la base de données avant de renvoyer une réponse au client.

- **Langages Front-end :**
  - **HTML (HyperText Markup Language) :** Structure la page web à l'aide de balises (`<html>`, `<head>`, `<body>`, `<h1>`, `<p>`, `<img>`, etc.) et d'attributs (`src`, `id`, `class`).
  - **CSS (Cascading Style Sheets) :** Gère la mise en forme visuelle et le style (couleurs, disposition, polices).
  - **JavaScript (JS) :** Rend la page dynamique et interactive en modifiant le DOM en temps réel, en gérant les événements (`onclick`, `onhover`) et en envoyant des requêtes de manière asynchrone.

- **Sécurité & Vulnérabilités côté client :**
  - **Exposition de données sensibles (Sensitive Data Exposure) :** Le code source livré au navigateur (HTML, commentaires HTML `<!-- -->`, fichiers JS) est accessible à tous. Y laisser des identifiants, liens internes cachés ou secrets constitue une faille critique.
  - **Injection HTML (HTML Injection) :** Survient lorsque des données fournies par l'utilisateur sont insérées directement dans le DOM (ex. via `innerHTML`) sans assainissement (*sanitization*). Un attaquant peut ainsi injecter du code HTML malveillant (liens, formulaires piégés) ou exécuter du JavaScript (Cross-Site Scripting - XSS).
