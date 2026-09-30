# Détection d'anomalies dans les logs par l'IA et le Big Data

Projet de fin d'études (PFE) du cycle ingénieur **ESEO**, spécialité Data & IA.

## Le projet

Les infrastructures informatiques modernes produisent d'énormes volumes de **logs** : des lignes de texte qui racontent tout ce qui se passe sur les serveurs. Les analyser à la main est impossible.

Nous construisons une plateforme qui **collecte, structure et analyse automatiquement** ces logs pour **détecter en quasi temps réel les anomalies et les incidents**, puis les afficher sur un tableau de bord et déclencher des alertes.

> **Question de recherche :** comment combiner le traitement distribué des logs et l'intelligence artificielle pour détecter automatiquement, en quasi temps réel, les anomalies d'une infrastructure à grande échelle ?

## Architecture

1. **Sources** : logs publics HDFS et logs simulés avec incidents injectés
2. **Ingestion** : Apache Kafka
3. **Traitement** : Apache Spark Structured Streaming
4. **Détection** : Isolation Forest, puis autoencoder et LSTM
5. **Stockage** : Elasticsearch
6. **Visualisation et alertes** : Kibana

## Technologies

| Rôle | Outil |
|---|---|
| Langage | Python |
| Streaming | Apache Kafka |
| Traitement distribué | Apache Spark |
| Machine learning | scikit-learn, PyTorch |
| Stockage et recherche | Elasticsearch |
| Visualisation | Kibana |
| Conteneurs | Docker |

## Organisation

Nous travaillons en **Scrum**, avec 6 sprints de 2 semaines, de septembre à décembre 2026.

| Sprint | Dates | Objectif |
|---|---|---|
| S0 | 28/09 → 11/10 | Cadrage : dépôt, données, environnement Docker |
| S1 | 12/10 → 25/10 | Prototype local : parsing et Isolation Forest |
| S2 | 26/10 → 08/11 | Pipeline temps réel avec Kafka et Spark |
| S3 | 09/11 → 22/11 | MVP complet : Elasticsearch, Kibana, alertes |
| S4 | 23/11 → 06/12 | Modèles avancés et évaluation |
| S5 | 07/12 → 20/12 | Rapports, documentation, soutenance |

## Installation

*Cette section sera complétée au fil des sprints.*

```bash
git clone https://github.com/nono-yann/pfe-anomalies-logs.git
cd pfe-anomalies-logs
```

## Équipe

| Membre | Rôle |
|---|---|
| Yann Monkam Nono | Product Owner & développeur |
| Gareth | Scrum Master & développeurs |
| Darelle | Scrum Master & développeur |

## Livrables

- [ ] Rapport bibliographique (état de l'art)
- [ ] Pipeline de collecte et de traitement des logs
- [ ] Modèles de détection entraînés et évalués
- [ ] Tableau de bord et système d'alerte
- [ ] Rapport expérimental
- [ ] Code source documenté