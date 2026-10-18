# Writeup TryHackMe : DNS in Detail

- **Parcours :** Pre-Security
- **Date :** 18/10/2026
- **Module :** 6) How The Web Works
- **Niveau :** Facile

---

## Objectifs de la Room
Comprendre le fonctionnement complet du protocole DNS (Domain Name System), la structure hiérarchique des domaines, les différents types d'enregistrements DNS et la résolution de nom pas à pas.

---

## Notions Clés

- **Fonction du DNS :**
  - Associe des noms de domaine intelligibles par l'humain (ex. `tryhackme.com`) à des adresses IP compréhensibles par les machines (ex. `104.26.10.229`).

- **Hiérarchie du domaine :**
  - **Root Domain (`.`) :** Racine de la hiérarchie DNS.
  - **TLD (Top-Level Domain) :** Extensions de premier niveau. On distingue les **gTLD** (ex. `.com`, `.org`) et les **ccTLD** (ex. `.fr`, `.co.uk`).
  - **Second-Level Domain :** Le nom principal choisi (ex. `tryhackme` dans `tryhackme.com`). Limité à 63 caractères.
  - **Subdomain :** Sous-domaine situé à gauche (ex. `admin` dans `admin.tryhackme.com`).
  - **Taille max :** Un nom de domaine complet ne peut pas dépasser 253 caractères.

- **Principaux enregistrements DNS :**
  - **A :** Associe un nom de domaine à une adresse **IPv4**.
  - **AAAA :** Associe un nom de domaine à une adresse **IPv6**.
  - **CNAME :** Redirige un nom de domaine vers un autre nom de domaine (alias).
  - **MX :** Spécifie les serveurs de messagerie gérant les e-mails du domaine (avec notion de priorité numérique).
  - **TXT :** Stocke du texte libre (utilisé pour la vérification de propriété, SPF, DKIM, DMARC).

- **Processus de résolution DNS :**
  1. **Cache local :** Le système vérifie d'abord son propre cache.
  2. **Recursive DNS Server :** Généralement fourni par le FAI ou configuré manuellement (ex. 8.8.8.8), il interroge les autres serveurs pour le compte du client.
  3. **Root DNS Server :** Oriente vers le serveur TLD correspondant (`.com`, `.net`, etc.).
  4. **TLD DNS Server :** Redirige vers le serveur de noms faisant autorité.
  5. **Authoritative DNS Server :** Héberge la zone DNS du domaine et renvoie la réponse finale (associée à une durée de mise en cache **TTL** - *Time To Live*).
