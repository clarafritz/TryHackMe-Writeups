# Writeup TryHackMe : Crack the Hash

- **Parcours :** Cyber Security 101
- **Module :** Cryptography
- **Date :** 17/11/2026
- **Niveau :** Débutant

---

## Objectifs de la Room

Apprendre à identifier différents types de hashes et à utiliser Hashcat pour retrouver des mots de passe à l'aide d'attaques par dictionnaire, avec ou sans salt.

## Notions clés

### 1. Identification des hashes
- **MD4 / MD5 :** empreintes de 128 bits (32 caractères hexadécimaux).
- **SHA-1 :** empreinte de 160 bits (40 caractères hexadécimaux).
- **SHA-256 :** empreinte de 256 bits (64 caractères hexadécimaux).
- **SHA-512 :** empreinte de 512 bits (128 caractères hexadécimaux).
- **NT hash :** dérivé de MD4, utilisé pour les mots de passe Windows.
- **bcrypt :** algorithme de hachage de mots de passe avec salt et facteur de coût, reconnaissable notamment par `$2a$`, `$2b$` ou `$2y$`.

### 2. Hashcat
- Outil de cassage de mots de passe à partir de hashes.
- **`-m` :** sélection du type de hash.
- **`-a 0` :** attaque par dictionnaire.
- **rockyou.txt :** liste de mots de passe couramment utilisée.
- **Cracked :** mot de passe retrouvé.
- **Exhausted :** tous les candidats ont été testés sans correspondance.

### 3. Salt et SHA-512crypt
- **Salt :** valeur utilisée avec le mot de passe lors du hachage.
- **`hash:salt` :** format attendu par certains modes Hashcat.
- **SHA-512crypt :** format de hachage utilisé sur les systèmes Unix/Linux.
- **`$6$` :** préfixe permettant de reconnaître SHA-512crypt.
- **Mode 1800 :** Hashcat extrait automatiquement le salt du hash SHA-512crypt complet.

### 4. HMAC-SHA1
- **HMAC :** mécanisme d'authentification utilisant une fonction de hachage et une clé secrète.
- **HMAC-SHA1 :** utilise SHA-1 dans une construction HMAC.
- **Mode 150 :** HMAC-SHA1 avec le mot de passe candidat comme clé.
- **Mode 160 :** HMAC-SHA1 avec le mot de passe candidat comme message.
- **Différence :** HMAC-SHA1 n'est pas équivalent à un simple SHA-1 avec salt.
