# Investigating Neighbourhood Unemployment in England Through Machine Learning and Spatial Analysis

## MSc Data Science Dissertation

This repository contains the code, datasets, model outputs and supporting analytical materials developed for my MSc Data Science dissertation at the University of East London.

The project investigates neighbourhood-level unemployment across England using machine learning, explainable AI and spatial analysis. The analysis is conducted at the Lower Layer Super Output Area (LSOA) level, allowing socio-economic differences to be examined at a detailed geographical scale.

## Project Overview

The study integrates Census 2021 data, the English Indices of Multiple Deprivation (IMD) 2019 and population-density data to construct an analytical dataset covering **31,810 LSOAs across England**.

The analysis examines the relationship between unemployment and a range of neighbourhood characteristics, including:

- labour-market participation
- income and deprivation
- educational attainment
- health and disability
- housing and tenure
- transport and car availability
- migration
- ethnicity
- demographic structure
- population density

Machine learning models are used to predict neighbourhood unemployment rates and identify the variables that contribute most strongly to prediction. QGIS is used alongside the modelling to examine geographical patterns in unemployment and selected socio-economic characteristics.

## Research Objectives

The project aims to:

1. Construct an integrated England-wide LSOA dataset using official Census, deprivation and population data.
2. Examine the relationship between unemployment and key socio-economic characteristics, including migration indicators.
3. Develop and compare machine learning models for predicting neighbourhood unemployment.
4. Identify the predictors making the greatest contribution to model predictions using feature importance and SHAP.
5. Examine geographical patterns of unemployment and selected socio-economic characteristics using spatial analysis in QGIS.

## Data Sources

The project primarily uses:

- **Census 2021** neighbourhood-level socio-economic and demographic data
- **English Indices of Multiple Deprivation (IMD) 2019**
- **Population-density data**

The datasets were integrated at the LSOA level using LSOA codes as the common geographical identifier.

The final analytical dataset contains **31,810 LSOAs** and **16 selected predictors** used for machine learning.

## Machine Learning

Four regression approaches were evaluated:

- Linear Regression
- Random Forest
- XGBoost
- LightGBM

The data were divided into training and testing sets using an **80/20 split**, and ensemble models were additionally evaluated following hyperparameter tuning.

Model performance was assessed using:

- Root Mean Squared Error (RMSE)
- Mean Absolute Error (MAE)
- R²
- Adjusted R²

## Model Performance

The ensemble models outperformed Linear Regression, demonstrating the value of modelling non-linear relationships between neighbourhood characteristics and unemployment.

| Model | RMSE | MAE | R² |
|---|---:|---:|---:|
| Linear Regression | 1.2626 | 0.9524 | 0.7652 |
| Random Forest (Tuned) | 1.1190 | 0.8495 | 0.8155 |
| XGBoost (Tuned) | **1.1033** | **0.8391** | **0.8207** |
| LightGBM (Tuned) | 1.1090 | 0.8438 | 0.8188 |

Among the evaluated models, **tuned XGBoost produced the strongest test-set predictive performance**, although the differences between the ensemble models were relatively small.

## Explainable AI

Feature importance and **SHAP (SHapley Additive exPlanations)** were used to interpret model predictions.

The analysis indicated that several structural socio-economic characteristics were particularly influential, including:

- **Never Worked Rate**
- **No Car or Van Rate**
- **Income Deprivation Score**

Other characteristics, including educational attainment, disability, housing, demographic composition and population density, also contributed to the predictive models.

Migration indicators provided predictive information but were less influential than the leading structural socio-economic characteristics after the other selected predictors were considered.

These results describe predictive relationships and should not be interpreted as evidence of causation.

## Spatial Analysis

QGIS was used to investigate the geographical distribution of unemployment and selected influential predictors across England.

The spatial analysis included individual choropleth maps for:

- Unemployment Rate
- Never Worked Rate
- Income Deprivation Score
- No Car or Van Rate

Bivariate choropleth maps were also used to examine geographical overlap between unemployment and selected socio-economic characteristics.

The maps demonstrate substantial geographical variation in unemployment and related neighbourhood disadvantage across England.

## Repository Structure

```text
england-neighbourhood-unemployment-ml/
│
├── 01_Data/
│   ├── Raw/
│   └── Processed/
│
├── 02_Output/
│   ├── Raw_Data_Inspection/
│   ├── Before_Treatment_EDA/
│   ├── After_Treatment_EDA/
│   ├── Correlation/
│   ├── Data_Treatment/
│   ├── Variable_Selection/
│   ├── Machine_Learning/
│   ├── Model_Comparison/
│   ├── Feature_Importance/
│   └── SHAP/
│
├── 03_Models/
│   ├── LightGBM_Tuned.pkl
│   ├── Linear_Regression.pkl
│   ├── Linear_Regression_Scaler.pkl
│   └── XGBoost_Tuned.pkl
│
├── DS7010_Dissertation_ML_Workflow.ipynb
├── DS7010_Dissertation_ML_Workflow.txt
├── Final SQL.txt
├── finalSQLdissertation.db
├── finalSQLdissertation.sqbpro
├── qgisfinal.qgz
├── u3064995_DS7010_final.pdf
├── .gitignore
└── README.md
```

> **Note:** The tuned Random Forest model file is not included in the repository because the serialized model is approximately 658 MB. Random Forest results, evaluation figures and feature-importance outputs are retained in `02_Output/`.

## Technologies and Tools

The project was developed using:

- **Python**
- **Google Colab / Jupyter Notebook**
- **Pandas**
- **NumPy**
- **Scikit-learn**
- **XGBoost**
- **LightGBM**
- **SHAP**
- **Matplotlib**
- **SQL / SQLite**
- **QGIS**

## Reproducibility

The main machine learning workflow is available in:

`DS7010_Dissertation_ML_Workflow.ipynb`

A text version of the workflow is also included:

`DS7010_Dissertation_ML_Workflow.txt`

The repository additionally contains processed datasets, model evaluation outputs, visualisations, selected trained models, SQL materials and the QGIS project used during the dissertation.

## Key Findings

The main findings of the study were:

- Ensemble machine learning models provided better predictive performance than Linear Regression.
- Tuned XGBoost achieved the strongest test performance with **R² = 0.8207** and **RMSE = 1.1033**.
- Never Worked Rate, No Car or Van Rate and Income Deprivation Score were among the most influential predictors.
- Migration indicators were comparatively less influential after accounting for the wider set of socio-economic characteristics.
- Unemployment and related socio-economic disadvantage displayed substantial geographical variation across English neighbourhoods.

Overall, the findings suggest that neighbourhood unemployment is associated with multiple interconnected socio-economic characteristics rather than a single factor.

## Important Interpretation

This project is based primarily on cross-sectional neighbourhood-level data. The machine learning models identify statistical and predictive relationships but **do not establish causal relationships**.

The findings should therefore be interpreted at the neighbourhood level and should not be used to make conclusions about individual residents.

## Dissertation

The final MSc dissertation is included in this repository as:

`u3064995_DS7010_final.pdf`

**University of East London**  
**MSc Data Science**
