# Writeup TryHackMe : Windows PowerShell

* **Parcours :** Cyber Security 101
* **Date :** 01/11/2026
* **Module :** 4) Command Line
* **Niveau :** Facile / Débutant

---

## Objectifs de la Room
Découvrir et maîtriser l'environnement d'automatisation et de gestion de système Microsoft PowerShell. L'objectif est de comprendre la structure orientée objet de PowerShell, de savoir utiliser les cmdlets de base pour explorer le système de fichiers, de filtrer et trier les données, d'analyser le système en temps réel et d'exécuter des commandes à distance.

---

## Notions Clés

* **Présentation et Architecture Orientée Objet :**
  * **Origine & Rôle :** Développé par Jeffrey Snover chez Microsoft pour dépasser les limitations de l'invite de commandes traditionnelles (`cmd.exe`).
  * **Approche Objet :** Contrairement à d'autres shells qui renvoient du texte brut, PowerShell manipule des objets .NET structurés dotés de **propriétés** (caractéristiques) et de **méthodes** (actions).
  * **Cmdlets :** Commandes natives structurées selon la convention **Verbe-Nom** (ex. `Get-Content`, `Set-Location`).

* **Aide et Découverte de Commandes :**
  * `Get-Command` : Recherche et liste les cmdlets, fonctions ou alias disponibles.
  * `Get-Help <cmdlet>` : Affiche la documentation et les paramètres d'une commande. L'option `-Examples` permet d'obtenir des cas d'usage pratiques.
  * `Get-Alias` : Liste les raccourcis configurés pour faciliter la transition depuis d'autres shells (`dir` pour `Get-ChildItem`, `cd` pour `Set-Location`, `cat` / `type` pour `Get-Content`).

* **Navigation et Manipulation du Système de Fichiers :**
  * **Exploration & Déplacement :** `Get-ChildItem` (liste les éléments) et `Set-Location` (change de répertoire courant).
  * **Gestion d'éléments :** `New-Item` (crée des fichiers/dossiers), `Remove-Item` (supprime), `Copy-Item` et `Move-Item` (copie et déplace).
  * **Lecture de contenu :** `Get-Content` lit et affiche le contenu texte des fichiers.

* **Pipeline, Filtrage et Tri des Données :**
  * **Chaînage par Pipeline (`|`) :** Transmet des objets complets de sortie d'une cmdlet vers l'entrée d'une autre.
  * **Tri :** `Sort-Object` trie les objets reçus selon une propriété donnée (ex. `Length` pour la taille).
  * **Filtrage :** `Where-Object` filtre la sortie selon des conditions précises à l'aide d'opérateurs de comparaison (`-eq`, `-ne`, `-gt`, `-ge`, `-lt`, `-le`, `-like`).
  * **Sélection :** `Select-Object` permet de restreindre l'affichage à des propriétés spécifiques.
  * **Recherche textuelle :** `Select-String` analyse le texte ou les fichiers pour repérer des motifs ou des expressions régulières (`regex`).

* **Informations Système et Réseau :**
  * **Métadonnées système :** `Get-ComputerInfo` rassemble les détails globaux du matériel, du BIOS et du système d'exploitation.
  * **Comptes locaux :** `Get-LocalUser` liste les utilisateurs locaux, leur état d'activation (`Enabled`) ainsi que leur description.
  * **Configuration réseau :** `Get-NetIPConfiguration` et `Get-NetIPAddress` affichent les adresses IP, passerelles, masques et serveurs DNS configurés sur les cartes réseau.

* **Analyse Temps Réel et Flux de Données :**
  * **Processus & Services :** `Get-Process` (surveille les processus actifs, PID et utilisation mémoire) et `Get-Service` (analyse l'état des services système).
  * **Connexions réseau :** `Get-NetTCPConnection` liste les connexions TCP actives et leur identifiant de processus propriétaire (`OwningProcess`).
  * **Sécurité & Hash :** `Get-FileHash` calcule les empreintes cryptographiques des fichiers (SHA-256 par défaut). L'extraction sous forme de propriété `(Get-FileHash ...).Hash` ou le passage par `Format-List` (`fl`) permet d'afficher la totalité du hash sans tronquage par la console.
  * **Flux NTFS :** `Get-Item -Stream *` permet d'inspecter les flux de données alternatifs (ADS - Alternate Data Streams).

* **Scripting et Exécution à Distance :**
  * **Rôle Défensif & Offensif :** Utilisé par la Blue Team (automatisation d'investigation, analyse de logs) et la Red Team (énumération, exécution à distance).
  * **Exécution distante (`Invoke-Command`) :** Permet d'exécuter un script local (`-FilePath`) ou un bloc de commandes (`-ScriptBlock { ... }`) sur une machine distante (`-ComputerName`).
