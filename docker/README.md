# Stack Docker — Détection d'anomalies dans les logs

## Démarrer la stack

cd docker
docker compose up -d

Premier démarrage : compter 2 à 3 minutes (téléchargement des images).
Démarrages suivants : 1 à 2 minutes (Elasticsearch et Kibana sont les plus lents).

## Arrêter la stack

docker compose down

## Vérifier l'état de tous les services

docker compose ps

Chaque service doit afficher "healthy" dans la colonne STATUS,
sauf spark-worker qui affiche seulement "Up" (pas de healthcheck
configuré pour ce service, voir plus bas).

## Vérification détaillée par service

### Kafka
- Port : 9092
- Commande de vérification :
  docker exec kafka /opt/kafka/bin/kafka-broker-api-versions.sh --bootstrap-server localhost:9092
- Résultat attendu : liste des versions d'API Kafka, sans erreur

### Elasticsearch
- Port : 9200
- Interface : http://localhost:9200
- Commande de vérification :
  curl http://localhost:9200/_cluster/health
- Résultat attendu : "status":"green" ou "status":"yellow"

### Kibana
- Port : 5601
- Interface : http://localhost:5601
- Résultat attendu : la page d'accueil "Welcome to Elastic" s'affiche

### Spark (master + worker)
- Port master : 7077 (connexion interne), 8080 (interface web)
- Interface : http://localhost:8080
- Résultat attendu : "Status: ALIVE" et au moins 1 worker listé
  avec l'état "ALIVE" dans la section Workers

## Note sur spark-worker

Ce service n'a pas de healthcheck Docker car il n'expose pas
d'API facile à interroger. Sa bonne santé se vérifie via
l'interface web de spark-master (http://localhost:8080), qui
liste les workers connectés.

## Prérequis

- Docker Desktop installé avec le backend WSL2 (Windows)
- Au moins 6 Go de RAM alloués à Docker (voir fichier .wslconfig
  dans le dossier utilisateur Windows)