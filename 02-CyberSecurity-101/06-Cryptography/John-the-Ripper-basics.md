
# Writeup TryHackMe : John the Ripper — The Basics

- **Parcours :** Cyber Security 101
- **Module :** Cryptography
- **Date :** 16/11/2026
- **Niveau :** Débutant

---

## Objectifs de la Room

Apprendre à utiliser John the Ripper pour tester la robustesse des mots de passe à partir de différents types de hachages et de fichiers protégés.

## Notions clés

### 1. John the Ripper
- Outil de cassage de mots de passe à partir de hashes.
- Attaque par dictionnaire avec `rockyou.txt`.
- Identification des formats : MD5, SHA, NT, Whirlpool, etc.

### 2. Hashes Windows et Linux
- **NT hash :** format de hachage des mots de passe Windows.
- **SAM :** base Windows contenant les informations des comptes.
- **/etc/shadow :** stocke les hashes des mots de passe Linux.
- **unshadow :** combine les informations de `/etc/passwd` et `/etc/shadow`.

### 3. Single Crack et règles personnalisées
- `--single` : génère des candidats à partir des informations d'un compte.
- **Word mangling :** transformation de mots (majuscules, chiffres, symboles).
- **GECOS :** informations descriptives d'un compte UNIX.
- **john.conf :** configuration des règles personnalisées.

### 4. Fichiers protégés
- `zip2john` : prépare une archive ZIP pour John.
- `rar2john` : prépare une archive RAR pour John.
- `ssh2john` : prépare une clé privée SSH protégée par une passphrase.

## Commandes utilisées

```bash
# Attaque par dictionnaire
john --wordlist=/usr/share/wordlists/rockyou.txt hash.txt

# Préciser le format
john --format=raw-md5 --wordlist=rockyou.txt hash.txt

# Afficher les mots de passe retrouvés
john --show hash.txt

# Préparer les hashes Linux
unshadow passwd.txt shadow.txt > hashes.txt

# Mode Single Crack
john --single --format=raw-md5 hash.txt

# Règles personnalisées
john --wordlist=rockyou.txt --rules=MaRegle hash.txt

# Archives ZIP et RAR
zip2john secure.zip > zip_hash.txt
rar2john secure.rar > rar_hash.txt

# Clé privée SSH
python3 /opt/john/ssh2john.py id_rsa > ssh_hash.txt
```
