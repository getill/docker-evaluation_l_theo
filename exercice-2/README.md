1 Voir fichiers

2 Execution de bash : docker exec -it database bash
Connection à MYSQL : mysql -u root -p
Afficher les bases de données : SHOW DATABASES;
Utilisation de la base docker_doc_dev : USE docker_doc_dev;
Affichage des tables : SHOW TABLES;
Afficher le contenu de la table article : SELECT \* FROM article;

3 docker compose exec database mysqldump -u root -p my_database > dump.sql

4 Projet initialement configuré dans cette optique

5 URL locale : http://localhost:8088/
