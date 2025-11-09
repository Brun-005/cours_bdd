# Modèles de Bases de Données

### Définitions clés

- Base de données (DB) : Collection organisée d'informations.
- Système de gestion de base de données (SGBD / DBMS) : Logiciel permettant de créer, gérer et interagir avec une base de données.

### Le SGBD fournit :
- Une interface pour les utilisateurs.
- Des outils pour organiser et superviser les données.

---

## Types de modèles

### 1. Modèle relationnel
- Structure en tables avec des relations entre elles.
- Utilise le langage SQL pour interroger et manipuler les données.
- Exemples de SGBD : PostgreSQL, MySQL, Oracle Database.

### 2. Modèle non relationnel (NoSQL)
- Structure plus flexible, adaptée aux données non tabulaires.
- Types principaux :
  - Magasins de documents (ex : MongoDB)
  - Bases orientées colonnes (ex : Cassandra)
  - Magasins clé-valeur (ex : Redis)
  - Bases de graphes (ex : Neo4j)

### 3. Modèle multi-modèle
- Combine plusieurs types de structures (relationnel + NoSQL).


---

## À retenir

- Il n’existe pas de modèle universel : le choix dépend du type de données et des besoins du projet.
- Les bases relationnelles sont idéales pour des données bien structurées.
- Les bases NoSQL sont plus adaptées aux données volumineuses ou non structurées.
