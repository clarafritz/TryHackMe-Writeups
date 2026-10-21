# Writeup TryHackMe : Become a Hacker

- **Parcours :** Pre-Security
- **Date :** 21/10/2026
- **Module :** 7) Attacks and Defenses
- **Niveau :** Facile / Débutant

---

## Objectifs de la Room
Découvrir les fondements de la sécurité offensive et du piratage éthique, s'initier aux méthodologies d'évaluation d'applications web, utiliser des outils de sécurité professionnels (Gobuster, Hydra) et comprendre comment des failles isolées s'enchaînent pour compromettre un système.

---

## Notions Clés 

- **Sécurité Offensive & Piratage Éthique :** Démarche proactive et autorisée consistant à tester les systèmes pour identifier et corriger les vulnérabilités avant qu'elles ne soient exploitées par des cybercriminels
- **Périmètre & Autorisation :** Cadre strict définissant les limites des tests autorisés. L'autorisation explicite est l'élément légal fondamental qui distingue le hacking éthique d'une attaque criminelle
- **Découverte de Contenu Caché :** Recherche de pages, fichiers ou répertoires non liés publiquement qui exposent des fonctionnalités ou données sensibles
- **Enchaînement de Faiblesses (Effet Domino) :** Combinaison de failles mineures (ex. une page de connexion exposée + un mot de passe faible) permettant une intrusion complète
- **Attaque par Dictionnaire :** Test automatisé et systématique d'une liste de mots de passe préfinis sur un formulaire d'authentification

---

## Synthèse des commandes 

- **Énumération de répertoires web (Gobuster) :**
  gobuster dir --url http://www.onlineshop.thm/ -w /usr/share/wordlists/dirbuster/directory-list.txt
  
  - **Brute force d'authentification (Hydra) :**
  hydra -l admin -P passlist.txt www.onlineshop.thm http-post-form "/login:username=^USER^&password=^PASS^:F=incorrect" -V
  
