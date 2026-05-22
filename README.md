# system_cardiovasculaire
# Prédiction du Risque Cardiovasculaire

## Description du projet

Ce projet consiste à développer une plateforme Big Data et Machine Learning capable de prédire le risque cardiovasculaire d’un patient à partir de plusieurs données médicales.

Le système collecte les données de santé, les traite à travers une architecture Medallion (Bronze, Silver, Gold), puis entraîne un modèle de Machine Learning afin de détecter les patients présentant un risque cardiovasculaire élevé.

Une application web développée avec Flask permet ensuite à l’utilisateur de saisir ses informations médicales et d’obtenir une prédiction en temps réel.

Les prédictions sont également stockées dans une base de données SQLite afin de conserver un historique des résultats et permettre des analyses futures.

---

# Étapes de réalisation du projet

## Étape 1 — Collecte des données

Le projet commence par la récupération des données médicales à partir d’un dataset cardiovasculaire contenant plusieurs informations de santé :

- âge
- genre
- taille
- poids
- tension artérielle
- cholestérol
- glucose
- tabagisme
- alcool
- activité physique

Les données sont importées depuis des fichiers CSV.

---
## Étape 2 — Architecture Medallion

Le projet utilise une architecture Medallion composée de trois couches :

### Bronze Layer
Stockage des données brutes sans transformation.
<img width="1782" height="912" alt="image" src="https://github.com/user-attachments/assets/a608bc87-903f-49ee-8f25-0146f4377164" />


### Silver Layer
Nettoyage, transformation et préparation des données.
<img width="1832" height="852" alt="image" src="https://github.com/user-attachments/assets/9131a94a-b283-4c4a-90cb-53d0b263fc0b" />

### Gold Layer
Création des données finales prêtes pour le Machine Learning et l’analyse.
<img width="1847" height="652" alt="image" src="https://github.com/user-attachments/assets/85d31722-01b8-4a0d-9cf8-4f6dd9b4c369" />


---
## Étape 3 — Préparation des données

Plusieurs traitements ont été réalisés :

- suppression des valeurs incohérentes;
- normalisation des données;
- création du BMI;
- création des catégories BMI;
- sélection des variables importantes.

---

## Étape 4 — Entraînement du modèle Machine Learning

Un modèle Random Forest a été entraîné pour prédire le risque cardiovasculaire.

Le modèle retourne :
- risque faible;
- risque élevé.
<img width="1467" height="486" alt="image" src="https://github.com/user-attachments/assets/ea8d8453-d9b2-4384-a4c9-d9b456e3401d" />

---
## Étape 5 — Développement Backend

Une API Flask a été développée pour :

- recevoir les données utilisateur;
- charger le modèle ML;
- effectuer les prédictions;
- retourner les résultats.
  <img width="1500" height="970" alt="image" src="https://github.com/user-attachments/assets/469d878f-0cf0-41ac-8113-5a3ed6ad4273" />


---

## Étape 6 — Développement Frontend

Une interface web a été développée afin de permettre à l’utilisateur :

- de saisir ses données médicales;
- d’obtenir une prédiction;
- de visualiser les résultats.
  <img width="1592" height="801" alt="image" src="https://github.com/user-attachments/assets/6fa05d06-5871-45c2-8930-30654c5c800f" />
  <img width="1590" height="821" alt="image" src="https://github.com/user-attachments/assets/f895cedd-d572-4db1-95b0-29cbc640c908" />



---

## Étape 7 — Stockage des prédictions

Les prédictions sont sauvegardées dans une base SQLite afin de :

- conserver l’historique;
- analyser les résultats;
- construire un futur dashboard
