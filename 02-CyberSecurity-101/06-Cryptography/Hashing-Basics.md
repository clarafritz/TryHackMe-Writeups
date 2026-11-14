
# Writeup TryHackMe : Hashing Basics

- **Parcours :** Cyber Security 101
- **Date :** 14/11/2026
- **Module :** 6) Cryptography
- **Niveau :** Facile / Débutant

---

## Objectifs de la Room

Comprendre les fonctions de hachage et leurs applications en cybersécurité : stockage des mots de passe, reconnaissance et craquage de hashes, vérification d'intégrité.

---

## Notions clés

### Fonctions de hachage
- Empreinte de taille fixe, calcul déterministe et non réversible.
- Effet avalanche : une petite modification de l'entrée change fortement le hash.
- Collision : deux entrées différentes produisent la même empreinte.
- MD5 et SHA-1 ne sont plus considérés comme sûrs contre les collisions.

### Stockage des mots de passe
- Ne jamais stocker les mots de passe en clair.
- Salt : valeur aléatoire unique empêchant la réutilisation directe de tables pré-calculées.
- Algorithmes adaptés : Argon2id, bcrypt, scrypt, PBKDF2.
- Rainbow tables : structures pré-calculées facilitant la recherche de certains mots de passe non salés.

### Reconnaissance et craquage
- Identifier les hashes par leur préfixe, leur longueur et leur contexte.
- Linux : `/etc/shadow` ; Windows : SAM et hashes NT.
- Hashcat et John the Ripper : test de mots de passe candidats.
- Attaque par dictionnaire avec une wordlist comme `rockyou.txt`.

### Intégrité et HMAC
- SHA-256 permet de comparer les empreintes de fichiers.
- HMAC combine une fonction de hachage et une clé secrète pour vérifier l'intégrité et l'authenticité d'un message.

### Hachage, encodage et chiffrement
- Hachage : non réversible.
- Encodage : réversible sans clé (ex. Base64).
- Chiffrement : réversible avec une clé appropriée.

---

## Commandes utilisées

    md5sum fichier
    sha1sum fichier
    sha256sum fichier

    hashcat -m <mode> -a 0 hash.txt wordlist.txt
    hashcat -m <mode> hash.txt --show

    john --wordlist=wordlist.txt hash.txt
    john --show hash.txt

    base64 fichier.txt
    base64 -d fichier.txt

