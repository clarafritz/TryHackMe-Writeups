### Writeup TryHackMe : SQL Fundamentals
* **Parcours :** Cyber Security 101
* **Module :** 8) Web Hacking
* **Date :** 25/11/2026
* **Niveau :** Débutant

--------------------------------------------------------------------------------

#### Objectifs de la Room
Comprendre l'architecture des bases de données relationnelles et non relationnelles, maîtriser le langage SQL pour définir, interroger et manipuler des données via les opérations CRUD, ainsi que savoir combiner clauses, opérateurs et fonctions d'agrégation ou de chaînes de caractères.

#### Notions clés
##### 1. Architecture des bases de données
* **Base de données (BDD) :** ensemble organisé de données structurées ou non, facilement accessibles, manipulables et analysables.
* **Bases de données relationnelles (SQL) :** stockent des données fortement structurées sous forme de **tables** composées de **colonnes** (champs et types de données stricts) et de **lignes** (enregistrements individuels).
* **Bases de données non relationnelles (NoSQL) :** stockent des données aux formats variés ou non tabulaires (paires clé-valeur, documents JSON/BSON, graphes, colonnes larges).
* **Clé primaire (`PRIMARY KEY`) :** colonne garantissant l'unicité de chaque ligne au sein d'une table (une seule par table).
* **Clé étrangère (`FOREIGN KEY`) :** colonne faisant référence à la clé primaire d'une autre table afin d'établir une relation entre les deux tables.
* **SGBD (DBMS) :** logiciel servant d'interface entre l'utilisateur/application et la base de données (ex. MySQL, MariaDB, PostgreSQL, Oracle, MongoDB).

##### 2. Instructions de bases de données et de tables (DDL)
* **Connexion CLI MySQL :** `mysql -u <user> -p` .
* **Gestion des bases :**
  * `CREATE DATABASE <nom_bdd>;` : crée une nouvelle base de données.
  * `SHOW DATABASES;` : liste l'ensemble des bases disponibles sur le serveur.
  * `USE <nom_bdd>;` : sélectionne la base de données active pour les requêtes suivantes.
  * `DROP DATABASE <nom_bdd>;` : supprime définitivement une base de données.
* **Gestion des tables :**
  * `CREATE TABLE <nom_table> (<colonne> <type> <contraintes>, ...);` : crée une table avec ses types (`INT`, `VARCHAR(255)`, `DATE`, `TEXT`) et contraintes (`AUTO_INCREMENT`, `PRIMARY KEY`, `NOT NULL`).
  * `SHOW TABLES;` : affiche les tables de la base active.
  * `DESCRIBE <nom_table>;` (ou `DESC`) : détaille la structure des colonnes d'une table.
  * `ALTER TABLE <nom_table> ADD <colonne> <type>;` : modifie la structure d'une table existante.
  * `DROP TABLE <nom_table>;` : supprime une table.

##### 3. Opérations CRUD (DML)
* **Create (`INSERT INTO`) :** ajoute un nouvel enregistrement dans une table (`INSERT INTO table (col1, col2) VALUES (val1, val2);`).
* **Read (`SELECT`) :** extrait tout (`SELECT * FROM table;`) ou une sélection de colonnes (`SELECT col1, col2 FROM table;`).
* **Update (`UPDATE`) :** modifie des lignes existantes selon une condition (`UPDATE table SET col1 = val1 WHERE condition;`).
* **Delete (`DELETE`) :** supprime des enregistrements ciblés (`DELETE FROM table WHERE condition;`).

##### 4. Clauses SQL
* **`WHERE` :** filtre les lignes individuelles avant tout regroupement selon une ou plusieurs conditions.
* **`DISTINCT` :** élimine les doublons dans les résultats retournés (`SELECT DISTINCT col FROM table;`).
* **`GROUP BY` :** regroupe les lignes partageant une même valeur afin d'appliquer des fonctions d'agrégation.
* **`ORDER BY` :** trie les résultats par ordre croissant (`ASC`, par défaut) ou décroissant (`DESC`).
* **`HAVING` :** filtre les groupes de résultats **après** l'exécution d'un `GROUP BY` et d'une agrégation.

##### 5. Opérateurs logiques et de comparaison
* **Recherche de motifs (`LIKE`) :** filtre les chaînes de caractères à l'aide de jokers (`%` pour zéro, un ou plusieurs caractères ; ex. `LIKE "%0"` pour ce qui finit par `0`).
* **Opérateurs booléens :** `AND` (toutes les conditions vraies), `OR` (au moins une condition vraie), `NOT` (inverse la condition), `BETWEEN val1 AND val2` (plage inclusive).
* **Opérateurs de comparaison :** `=`, `!=` (ou `<>`), `<`, `>`, `<=`, `>=`.

##### 6. Fonctions de chaînes et d'agrégation
* **Manipulation de chaînes :**
  * `CONCAT(str1, str2, ...)` : fusionne plusieurs chaînes ou colonnes sur une même ligne.
  * `GROUP_CONCAT(col SEPARATOR " & ")` : concatène les valeurs de plusieurs lignes en une seule chaîne séparée par un délimiteur donné.
  * `SUBSTRING(col, debut, longueur)` : extrait une sous-chaîne de caractères.
  * `LENGTH(col)` : retourne le nombre de caractères d'une chaîne (espaces et ponctuation inclus).
* **Agrégation :**
  * `COUNT(*)` : compte le nombre total d'enregistrements.
  * `SUM(col)` : calcule la somme des valeurs numériques non nulles d'une colonne.
  * `MAX(col)` / `MIN(col)` : retourne respectivement la valeur maximale ou minimale d'une colonne.
