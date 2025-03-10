# Réponses aux questions

### 1

Un conteneur est une unité légère et isolée qui embarque une application et ses dépendances dans un environnement cohérent, reproductible et portable.

### 2

Non, Docker permet de simplifier l’utilisation des conteneurs Linux via son API tout en apportant des outils et un registre d’image.

### 3

Car il favorise l’éphémérité et la scalabilité des conteneurs, permettant de les recréer à la demande sans se soucier des données perdues.

### 4

Une image Docker, qui doit être légère, bien organisée et facile à reproduire.

### 5

docker run démarre un nouveau conteneur, docker exec lance une commande dans un conteneur déjà actif.

### 6

Oui, avec

```bash
docker exec.
```

### 7

Parce qu’il change tout le temps et peut casser l’appli si la version ne correspond plus.

### 8

La commande lance un conteneur en arrière-plan (-d), mappant le port 9001 de l’hôte au port 80 du conteneur, avec un volume monté sur /var/www/html, et utilisant l’image php:8.2-apache.

### 9

avec la commande

```bash
docker stop $(docker ps -q)
```

### 10

Il faut utiliser des images de base minimalistes (Alpine par exemple). Puis utiliser les Multistage builds pour éviter d’inclure des fichiers inutiles.

### 11

Oui, sauf si on utilise un volume.

### 12

Non, mais on peut en créer une nouvelle basée dessus.

### 13

Sur Docker Hub (docker push et docker pull).

### 14

scratch, elle est complètement vide.

### 15

Avec un socket Unix ou TCP. HTTP seul est bloqué car pas sécurisé.

### 16

CMD, car on peut le modifier au lancement.
