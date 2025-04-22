# erdos-2025-wildfire-structural-damage

## Wildfire Structural Damage Prediction (Erdös Institute Data Science Project Spring 2025)

Kevin Specht, Evan Ferguson, Ruichen Kong, Andres Barei, Kiana Burton

### Objectives

Our main objective is to discover correlations between features of structures affected by wildfires and whether those structures are likely to be destroyed by those wildfires. This will help to predict the level of danger buildings and, by extension, neighborhoods and cities face from wildfires from a structural perspective. It will also help to determine what factors may lead to structural damage from wildfires so that they can be mitigated in the future.

### Datasets

CAL FIRE Damage Inspection (DINS) Data: https://data.ca.gov/dataset/cal-fire-damage-inspection-dins-data \
Glossary of Dataset Definitions: https://gis.data.cnra.ca.gov/datasets/CALFIRE-Forestry::cal-fire-damage-inspection-dins-data/about (select DINS database dictionary link)\
This dataset includes structures impacted by wildfire, meaning they are inside or within 100 meters of the fire perimeter. The data was collected by CAL FIRE and partnering agencies on structures damaged and destroyed by wildfires and California from 2013 onwards (note that data on non-damaged structures was only collected from 2018 onwards). Each structure has information on structure type, construction features, location, level of damage, and other features included when available (or null if not). Levels of damage include no damage (0% damaged), affected damage (1-10% damaged), minor damage (10-25% damaged), major damage (25-50% damaged), and destroyed (50-100% damaged). For our purposes, we will consider all damage levels other than destroyed to be not destroyed.

### Stakeholders

- City planners, building inspectors, and other government workers determining how to make buildings and cities more durable against wildfires
- Real estate/insurance agents appraising a building's value in the context of wildfire risk
- Homeowners/renters determining their building's level of safety against wildfires
- Emergency workers determining how wildfires are likely to impact the zones they're operating in

### Key Performance Indicators (KPI)

- The main performance indicator will be the accuracy of predictions for whether a building will be destroyed by a wildfire when compared whether it was actually destroyed.

### File Organization
This repository is divided into four folders:

#### data
- cal_fire_data.csv contains the raw, untouched data on structural damage from wildfires downloaded from the CAL FIRE database
- cal_fire_data_cleaned.csv contains the cleaned data on structural damage from wildfires obtained after running the Data_cleaning notebook

#### cleaning (start here before running eda/models)
- Data_cleaning.ipynb will clean the cal_fire_data.csv file in the data folder and save the output to the cal_fire_data_cleaned.csv file in the data folder

#### eda (only run after cleaning data)
- Data_eda.ipynb will perform exploratory data analysis (EDA) on the cleaned data from cal_fire_data_cleaned.csv, displaying relationships in the data via various graphs

#### models (only run after cleaning data)
- Baseline_model.ipynb will predict whether buildings will be destroyed by wildfires based on simple model (selects most frequent class out of destroyed/not destroyed) and displays metrics
- Logistic_regression.ipynb will predict whether buildings will be destroyed by wildfires based on logistic regression model (after selecting most important features), displays metrics, and determines feature importance
- KNN_model_hyperparameter_and_variable_tuning.ipynb will build a model to predict whether buildigns will be destroyed by wildfires using K-Nearest Neighbors (KNN) by tuning various hyperparameters
- KNN_model.ipynb will predict whether buildings will be destroyed by wildfires based on KNN model (after selecting most important features) and displays metrics 
- Naive_bayes.ipynb will predict whether buildings will be destroyed by wildfires based on Naive Bayes model (after selecting most important features) and displays metrics
- Decision_tree.ipynb will predict whether buildings will be destroyed by wildfires based on decision tree model, displays metrics, and determines feature importance
- Random_forest.ipynb will predict whether buildings will be destroyed by wildfires based on random forest model, displays metrics, and determines feature importance
- Extra_trees.ipynb will predict whether buildings will be destroyed by wildfires based on extra trees model, displays metrics, and determines feature importance
- Gradient_boosting.ipynb will predict whether buildings will be destroyed by wildfires based on gradient boosting model, displays metrics, and determines feature importance
- Model_Comparison.ipynb will compare the metrics obtained by predicting building destruction across all models
