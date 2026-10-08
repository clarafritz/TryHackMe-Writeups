# Writeup TryHackMe : Introduction to Defensive Security

- **Parcours :** Pre-Security
- **Date :** 08/10/2026
- **Module :** 1) Introduction to Cyber Security
- **Niveau :** Facile / Débutant

---

## Objectifs de la Room
Comprendre la définition de la **sécurité défensive** (*Blue Teamer*), découvrir les concepts d'**analyse de logs** et de **détection d'incidents**, puis analyser le trafic réseau pour identifier une attaque et défendre une infrastructure ciblée.

---

## Notions Clés 
  - **Sécurité Défensive (Blue Team) :** Ensemble des pratiques et mesures visant à surveiller, détecter, analyser et bloquer les attaques informatiques pour protéger une infrastructure.
  - **SOC (Security Operations Center) :** Centre d'opérations dédié à la surveillance continue de la sécurité des systèmes d'information et à la gestion des incidents.
  - **Analyse de Logs & Trafic :** Inspection des journaux d'événements et des requêtes réseau (URL, méthodes HTTP, codes d'erreur) pour identifier des comportements suspects (*fuzzing*, tentatives d'intrusion).
  - **Pare-feu (Firewall) & Confinement :** Application de règles de blocage (ex: bannir une adresse IP malveillante) pour stopper immédiatement une attaque en cours.

---

## Synthèse des commandes 
- **Dashboard SOC / SIEM :** Visualisation centralisée des alertes de sécurité, analyse des adresses IP sources et suivi des tentatives d'accès non autorisées (codes HTTP `404`, `403`).
- **Pare-feu (Firewall) :**
    - Action : `BLOCK` sur l'IP source `32.122.195.63` pour interdire tout accès futur.

