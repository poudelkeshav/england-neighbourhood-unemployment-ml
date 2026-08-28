# Investigating Neighbourhood Unemployment in England Through Machine Learning and Spatial Analysis

## MSc Data Science Dissertation

This repository contains the code and supporting analytical materials developed for my MSc Data Science dissertation at the University of East London.

The study investigates socio-economic characteristics associated with unemployment across English Lower Layer Super Output Areas (LSOAs) using machine learning and spatial analysis.

## Project Overview

The research integrates official Census 2021, English Indices of Multiple Deprivation (IMD) 2019 and population-density data to construct an analytical dataset covering 31,810 English LSOAs.

The analysis examines how neighbourhood-level characteristics relating to deprivation, labour-market participation, education, health, housing, transport accessibility, migration, ethnicity and demographic structure are associated with unemployment.

## Research Objectives

The main objectives of the study are to:

1. Construct an integrated England-wide LSOA dataset using official Census, deprivation and population data.
2. Examine relationships between unemployment and key socio-economic characteristics, including migration indicators.
3. Develop and compare predictive models of neighbourhood unemployment.
4. Identify the variables making the greatest contribution to unemployment prediction.
5. Examine geographical patterns of unemployment and selected socio-economic characteristics using QGIS.

## Machine Learning Models

Four regression approaches were evaluated:

- Linear Regression
- Random Forest
- XGBoost
- LightGBM

Model performance was compared using:

- Root Mean Squared Error (RMSE)
- Mean Absolute Error (MAE)
- R²
- Adjusted R²

Hyperparameter tuning was applied to the ensemble models using cross-validation.

## Model Interpretation

Feature importance and SHAP (SHapley Additive exPlanations) were used to interpret the best-performing machine learning model and assess the predictive contribution of the selected socio-economic characteristics.

## Spatial Analysis

QGIS was used to examine the geographical distribution of unemployment and selected influential predictors across English LSOAs.

The spatial analysis included:

- Unemployment Rate
- Never Worked Rate
- Income Deprivation Score
- No Car or Van Rate
- Bivariate choropleth analysis

## Key Findings

The ensemble machine learning models outperformed Linear Regression.

Tuned XGBoost achieved the strongest predictive performance:

| Metric | Result |
|---|---:|
| RMSE | 1.1033 |
| MAE | 0.8391 |
| R² | 0.8207 |
| Adjusted R² | 0.8202 |

The most influential predictors included:

- Never Worked Rate
- Income Deprivation Score
- No Car or Van Rate

Migration indicators contributed predictive information but were less influential than the leading structural socio-economic characteristics.

The spatial analysis also identified substantial geographical variation in unemployment and related neighbourhood disadvantage across England.

## Technologies and Tools

- Python
- Google Colab
- Pandas
- NumPy
- Scikit-learn
- XGBoost
- LightGBM
- SHAP
- Matplotlib
- QGIS
- SQL

## Repository Structure

```text
england-neighbourhood-unemployment-ml/
│
├── README.md
├── notebooks/
│   └── dissertation_analysis.ipynb
│
├── data/
│   └── README.md
│
├── outputs/
│   ├── figures/
│   ├── model_results/
│   └── spatial_analysis/
│
└── requirements.txt
