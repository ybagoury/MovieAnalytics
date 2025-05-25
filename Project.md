# 🎬 Projet Data Engineering : Plateforme d'Analytique de Films (Microsoft Fabric)

Ce projet met en œuvre une architecture complète Lakehouse dans Microsoft Fabric autour d'un cas d'usage cinématographique. Il permet d'intégrer, transformer et analyser des données sur les films et les utilisateurs à l’aide de notebooks PySpark, d’une API externe et d’un modèle en étoile.

## 📁 Architecture

- **Bronze Layer** :
  - `bronze_movies_metadata` : Données brutes CSV depuis Kaggle
  - `bronze_user_ratings` : Données simulées (500 notations réalistes)
  - `bronze_omdb_api_ratings` : Réalisateurs enrichis via l’API OMDb

- **Silver Layer** :
  - `silver_movies_cleaned` : Films nettoyés avec IMDb ID extrait, budget, durée, etc.
  - `silver_user_ratings` : Notations avec `user_id`, `imdb_id`, `rating`, `timestamp`
  - `silver_omdb_api` : Table simplifiée avec `imdb_id` + `director`

- **Gold Layer** :
  - `gold_movie_rating_stats` : Moyenne et nombre de votes par film
  - `gold_top_movies` : Top 50 films les mieux notés avec +20 votes
  - `gold_user_activity` : Total de notations et dernière activité utilisateur
  - `dim_user` : Clé technique `user_sk`
  - `dim_movie` : Clé technique `movie_sk`
  - `fact_movie_ratings` : Table de faits avec clés techniques + rating

## 🛠️ Technologies

- Microsoft Fabric (Lakehouse, Notebooks, Delta Tables)
- Python (PySpark, pandas)
- OMDb API (https://www.omdbapi.com)
- GitHub pour versionnement
- Power BI (connexion prévue au Gold Layer)

## 🚀 Comment exécuter

1. Cloner ce repo dans Microsoft Fabric
2. Charger le fichier CSV `movie_metadata.csv` dans la zone Files
3. Lancer les notebooks étape par étape :
   - Nettoyage & création Bronze
   - Enrichissement OMDb
   - Création des Silver et des Gold
4. Analyser les résultats dans Power BI

## 👨‍💻 Membres du projet

- BEN AYED Mohamed Aziz
- ALBAGOURY Youssef

