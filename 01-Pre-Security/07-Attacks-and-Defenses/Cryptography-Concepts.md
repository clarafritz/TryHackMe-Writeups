# Writeup TryHackMe : Cryptography Concepts

- **Parcours :** Pre-Security
- **Date :** 20/10/2026
- **Module :** 7) Attacks and Defenses
- **Niveau :** Facile

---

## Objectifs de la Room
Comprendre les concepts fondamentaux de la cryptographie, la distinction essentielle entre le chiffrement symétrique et le chiffrement asymétrique, le problème du partage sécurisé des clés, ainsi que le fonctionnement combiné (approche hybride) de ces technologies dans des protocoles réels comme HTTPS.

---

## Notions Clés

- **Bases de la Cryptographie :**
  - **Définition :** Utilisation de règles mathématiques et de clés secrètes pour protéger les données et détecter les falsifications lors du transit sur Internet
  - **Texte brut (Plaintext) :** Le message lisible original 
  - **Texte chiffré (Ciphertext) :** Version brouillée inintelligible sans la clé appropriée 
  - **Clé (Key) :** L'élément secret déterminant le fonctionnement du chiffrement et du déchiffrement
  - **Algorithme :** La méthode publique expliquant comment appliquer la clé sur le message

- **Chiffrement Symétrique :**
  - **Définition :** Utilise une **seule et même clé** partagée pour verrouiller (chiffrer) et déverrouiller (déchiffrer) le message
  - **Exemple pratique :** Le chiffrement de César, qui décale chaque lettre de l'alphabet d'un nombre fixe de positions (la clé)
  - **Avantages & Limites :** Très rapide et adapté au traitement de données en masse[cite: 6, 9], mais nécessite de trouver un moyen sûr de transmettre la clé secrète au destinataire au préalable (problème de distribution des clés)

- **Chiffrement Asymétrique :**
  - **Définition :** Utilise une paire de clés mathématiquement liées : une **clé publique** (accessible à tous) pour chiffrer et une **clé privée** (gardée secrète) que seul le destinataire possède pour déchiffrer
  - **Avantage principal :** Résout le problème du partage de clé, car la clé publique peut être diffusée ouvertement sans compromettre la sécurité du déchiffrement

- **Utilisation Concrète et Approche Hybride (HTTPS) :**
  - **Définition :** Combinaison du chiffrement asymétrique et symétrique pour allier sécurité et rapidité lors de la navigation web
  - **Fonctionnement :** Le chiffrement **asymétrique** est utilisé initialement pour convenir d'un secret partagé en toute sécurité, puis le chiffrement **symétrique** prend le relais pour gérer le trafic en masse de la session
  - **Certificats Numériques :** Documents signés par une Autorité de Certification (AC) de confiance permettant de vérifier qu'une clé publique appartient bien au véritable site web et non à un attaquant
