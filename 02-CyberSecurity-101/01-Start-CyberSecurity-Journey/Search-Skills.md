# Writeup TryHackMe : Search Skills

- **Parcours :** Cyber Security 101
- **Date :** 22/10/2026
- **Module :** 1) Start your cybersecurity journey
- **Niveau :** Facile / Débutant

---

## Objectifs de la Room
Apprendre à effectuer des recherches d'informations efficaces sur Internet en utilisant des moteurs de recherche spécialisés (Shodan), des bases de données de menaces et de vulnérabilités (VirusTotal, NVD/CVE), ainsi que la documentation technique (pages de manuel Linux `man`) et des dépôts de code (GitHub).

---

## Notions Clés

- **Moteurs de recherche spécialisés (Shodan / TryScanMe) :**
  - **Principe :** Analyse en permanence Internet pour indexer les équipements réseau, systèmes de contrôle industriels, serveurs web et objets connectés (IoT).
  - **Filtres de recherche :** Permettent d'affiner la recherche par pays (`country:`), par port spécifique (`port:`), par organisation/ASN (`org:`) ou par nom d'hôte (`hostname:`).

- **Analyse de menaces et fichiers (VirusTotal / TryDetectMe) :**
  - **Principe :** Centralise les analyses de dizaines de moteurs antivirus et de services de sécurité pour analyser des fichiers, des URLs, des domaines ou des hachages.
  - **Utilisation :** Permet d'obtenir un consensus rapide au sein de la communauté Blue Team pour déterminer si un fichier ou un lien est malveillant.

- **Bases de données de vulnérabilités (CVE & CVSS) :**
  - **CVE (*Common Vulnerabilities and Exposures*) :** Dictionnaire universel attribuant un identifiant unique aux vulnérabilités connues (ex. `CVE-YEAR-NUMBER`).
  - **CVSS (*Common Vulnerability Scoring System*) :** Score standardisé évaluant la sévérité d'une vulnérabilité en fonction de son impact, sa complexité et sa disponibilité.

- **Documentation technique & Pages de manuel (`man`) :**
  - **Pages MAN :** Documentation intégrée directement dans le terminal Linux pour consulter la syntaxe, les options et des exemples d'utilisation des commandes système.
  - **Outil Netcat (`nc`) :** Utilitaire en ligne de commande permettant de lire et d'écrire des données à travers des connexions réseau TCP ou UDP.

- **Recherche de PoC et outils sur GitHub :**
  - **Rôle en cybersécurité :** Plateforme où les chercheurs publient des preuves de concept (PoC), des scripts de détection et des rapports d'analyse de vulnérabilités.
  - **Mise en garde :** Toujours vérifier le code hébergé sur des dépôts publics avant exécution, certains PoC pouvant être incomplets ou malveillants.

---

## Synthèse des commandes & Pratique (Simulateur)

Dans cette salle, nous avons interagi avec plusieurs simulateurs et outils de recherche :

- **Énumération Shodan (TryScanMe) :**
  - Utilisation de la barre de recherche pour identifier des serveurs web (`apache`) et analyser les bannières HTTP, les adresses IP associés et les noms de domaine.

- **Analyse de bannières antivirus (TryDetectMe) :**
  - Soumission d'un nom d'exécutable suspect (`invoice_payment.exe`) pour évaluer le score de détection global fourni par les fournisseurs de sécurité.

- **Recherche de vulnérabilité (Database CVE) :**
  - Consultation des fiches détaillées de vulnérabilités (ex. `CVE-2026-1337`) pour extraire les métriques CVSS et comprendre l'impact système.

- **Consultation de manuel sous Linux :**
  - Affichage de la documentation d'une commande via le terminal :
    ```bash
    man nc
    ```
  - Exécution d'une connexion réseau de test basée sur les exemples du manuel :
    ```bash
    nc host.example.com 42
    ```

- **Analyse de dépôt GitHub :**
  - Recherche d'un identifiant CVE sur la plateforme pour analyser le fichier `README.md` et identifier le script de démonstration / PoC associé.
