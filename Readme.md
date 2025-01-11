# Guide d'Installation du Stack Elastic

Ce guide vous accompagnera dans la configuration du stack Elastic (Elasticsearch, Logstash, Kibana) à l'aide de Docker Compose. Le stack offre des outils puissants pour la gestion et l'analyse des données.

## Prérequis

- Docker et Docker Compose installés sur votre système.
- Connaissances de base en Docker et des composants Elasticsearch.

## Vue d'Ensemble

Le stack Elastic comprend les services suivants :

1. **Elasticsearch** : Le store de données central du stack.
2. **Logstash** : L'outil pour collecter, traiter et envoyer des données vers Elasticsearch.
3. **Kibana** : L'outil de visualisation permettant d'interagir avec les données stockées dans Elasticsearch.
4. **Setup** : Un service qui initialise les utilisateurs et rôles dans Elasticsearch au démarrage.

## Structure des Fichiers

Le setup utilise Docker Compose, avec des configurations stockées dans des fichiers `.env` et YAML.

- **.env** : Contient les variables de mots de passe pour différents utilisateurs.
- **docker-compose.yml** : Définit tous les services et leurs configurations.
- **setup/** : Contient les scripts et rôles pour configurer les utilisateurs dans Elasticsearch.

## Services

### 1. Service Setup

Le service `setup` exécute un script unique qui initialise les utilisateurs et rôles dans Elasticsearch. Ce service est uniquement nécessaire lors du premier démarrage et peut être ignoré lors des démarrages suivants.

Pour exécuter ce service :

```bash
docker-compose --profile setup up
