
# Writeup TryHackMe : Cryptography Basics

- **Parcours :** Cyber Security 101
- **Date :** 12/11/2026
- **Module :** 6) Cryptography
- **Niveau :** Facile / Débutant

---

## Objectifs de la Room

Découvrir les principes fondamentaux de la cryptographie, comprendre les différents types de chiffrement et les opérations mathématiques utilisées pour protéger les données.

---

## Notions Clés

### 1. Fondamentaux de la cryptographie

- **Confidentialité :** empêcher la lecture des données par des tiers.
- **Intégrité :** vérifier que les données n'ont pas été modifiées.
- **Authenticité :** vérifier l'origine des données.
- **Plaintext :** texte original lisible.
- **Ciphertext :** texte après chiffrement.
- **Encryption / Decryption :** chiffrement / déchiffrement.
- **Key :** clé utilisée par l'algorithme.

### 2. Chiffrement de César

Chiffrement par substitution utilisant un décalage fixe des lettres.

- Chiffrement : `C = (P + k) % 26`
- Déchiffrement : `P = (C - k) % 26`
- Seulement 25 décalages non triviaux : vulnérable à la force brute.

### 3. Chiffrement symétrique et asymétrique

**Symétrique :**
- Même clé secrète pour chiffrer et déchiffrer.
- Rapide, mais nécessite un partage sécurisé de la clé.
- Exemples : AES, DES, 3DES.
- AES est le standard moderne ; DES et 3DES sont obsolètes.

**Asymétrique :**
- Deux clés : publique et privée.
- Permet notamment de chiffrer avec la clé publique du destinataire.
- Exemples : RSA et cryptographie à courbes elliptiques (ECC).
- Diffie-Hellman permet d'établir un secret partagé.

### 4. Opération XOR

- OU exclusif : renvoie 1 si les bits sont différents, sinon 0.
- Propriété réversible : `(P ⊕ K) ⊕ K = P`.
- Opérateur Python : `^`.

### 5. Opération Modulo

- `%` retourne le reste d'une division entière.
- Exemple : `23 % 7 = 2`.
- Utilisé dans de nombreux algorithmes cryptographiques.

