
# Writeup TryHackMe : Public Key Cryptography Basics

- **Parcours :** Cyber Security 101
- **Date :** 13/11/2026
- **Module :** 6) Cryptography
- **Niveau :** Facile / Débutant

---

## Objectifs de la Room

Comprendre la cryptographie asymétrique, l'échange de clés et les mécanismes d'authentification utilisés dans les communications sécurisées.

---

## Notions Clés

### RSA
- Algorithme de cryptographie asymétrique.
- Clé publique `(n, e)` et clé privée `(n, d)`.
- `n = p × q` avec deux nombres premiers.
- `φ(n) = (p-1) × (q-1)`.
- Chiffrement : `c = m^e mod n`.
- Déchiffrement : `m = c^d mod n`.

### Diffie-Hellman
- Permet d'établir une clé secrète partagée sur un canal non sécurisé.
- Paramètres publics : `p` et `g`.
- Secrets privés : `a` et `b`.
- Clés publiques : `A = g^a mod p` et `B = g^b mod p`.
- Secret partagé : `K = B^a mod p = A^b mod p`.
- Python : `pow(base, exposant, modulo)`.

### SSH
- Authentification du serveur par sa clé publique.
- Authentification du client possible par paire de clés.
- `known_hosts` : clés des serveurs connus.
- `authorized_keys` : clés publiques autorisées.

```bash
ssh-keygen -t ed25519
ssh user@IP
ssh -i cle_privee user@IP
ssh-keygen -lf fichier_cle
```

### Signatures et certificats
- Signature numérique : authenticité et intégrité.
- Signature avec la clé privée, vérification avec la clé publique.
- Certificats TLS : associent un domaine à une clé publique.
- Chaîne de confiance : CA racine → CA intermédiaire → certificat serveur.

### PGP / GPG
- Chiffrement et signature de fichiers ou messages.
- Utilise des clés publiques et privées.

```bash
gpg --full-gen-key
gpg --import fichier.key
gpg --decrypt fichier.gpg
```

### Cryptanalyse
- **Force brute :** tester toutes les possibilités.
- **Attaque par dictionnaire :** tester des mots ou combinaisons probables.
