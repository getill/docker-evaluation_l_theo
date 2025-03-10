# Exercice 2

# Initialisation du projet

- Une fois cloné, assurez vous de vous mettre à la racine du projet

  - Executez Docker Desktop
  - Dans un terminal entrez l'une des deux commandes :

          Mode dev
        ```bash
            docker-compose -f docker-compose.yml -f docker-compose.override.yml up --build
        ```
          Mode prod
        ```bash
            docker-compose -f docker-compose.yml -f docker-compose.prod.yml up --build
        ```

  - Rendez vous à cette adresse pour accéder au contenu du php !
    http://localhost:8088/

  Si vous rencontrez des problèmes de connexion, il se peut que celà soit dû au fichier .env innexistant :

  - Créez un fichier ".env" à la racine de votre projet puis ajoutez les variables suivantes :

```bash
    MYSQL*ROOT_PASSWORD=\_Insérez votre mdp root*
    MYSQL*DATABASE=\_Insérez votre nom de base de données*
    MYSQL*USER=\_Insérez votre nom d'utilisateur*
    MYSQL*PASSWORD=\_Insérez votre mdp*
```

- Pensez à ajouter le .env dans le .gitignore

# Réponses aux questions

### 1

Voir fichiers

### 2

Execution de bash :

```bash
docker exec -it database bash
```

Connection à MYSQL :

```bash
mysql -u root -p
```

Afficher les bases de données :

```bash
SHOW DATABASES;
```

Utilisation de la base docker_doc_dev :

```bash
USE docker_doc_dev;
```

Affichage des tables :

```bash
SHOW TABLES;
```

Afficher le contenu de la table article :

```bash
SELECT \* FROM article;
```

### 3

```bash
docker compose exec database mysqldump -u root -p my_database > dump.sql
```

### 4

Projet initialement configuré dans cette optique

### 5

URL locale : http://localhost:8088/

### 6

Voir docker-compose

```bash
volumes: - ./client:/var/www/html
```

### 7

Pour démarrer l'environnement de dev :

```bash
docker-compose -f docker-compose.yml -f docker-compose.dev.yml up --build
```

Pour démarrer l'environnement de prod :

```bash
docker-compose -f docker-compose.yml -f docker-compose.prod.yml up --build
```

### 8

Il n'est évidemment pas recommandé de la faire en clair (raison pour laquel j'ai initialement pris soin de tout mettre dans un .env et que le git ignore ne prend pas en compte de ce fichier). La raison principale est que tout est accessible et visible par tous. La solution de docker est les secrets (plus sécurisé que .env). Les raisons pour leslquels les secrets sont plus sécurisés que les variables d'environnement sont :

- Le chiffrement des données.
- Decryptage uniquement lorsque les données sont utiles.
- Un accès très contrôlé. Les secrets sont accessibles uniquement aux conteneurs ou services qui les demandent explicitement, ce qui permet de mieux contrôler qui peut y accéder.
