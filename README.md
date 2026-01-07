# Multimodal House Price Prediction Using Tabular Data and Satellite Imagery

## Project Overview

This project aims to predict residential house prices using a multimodal machine learning approach that combines structured tabular data with satellite imagery. While tabular features capture intrinsic property characteristics such as size, number of rooms, and construction year, they do not fully represent neighborhood-level factors that influence property value.

Satellite images provide additional contextual information such as greenery, road connectivity, surrounding infrastructure, and spatial layout. By integrating both data sources, the model captures both property-level and environment-level signals, resulting in improved robustness and interpretability.

---

## Dataset Description

The dataset consists of two complementary components:

- **Tabular Data**  
  House-level attributes including living area, number of bedrooms, number of bathrooms, construction year, renovation year, and geographic coordinates.

- **Satellite Images**  
  High-resolution satellite images collected using latitude and longitude coordinates via the Mapbox Static Images API. These images capture neighborhood characteristics such as vegetation cover, building density, and road structure.

The training dataset contains house prices as the target variable, while the test dataset contains only input features.

---

## Methodology

The overall workflow of the project is summarized below:

1. Satellite image collection using geographic coordinates  
2. Tabular data preprocessing and feature scaling  
3. Baseline model training using only tabular data  
4. Image feature extraction using a pretrained CNN (ResNet50)  
5. Feature fusion of tabular and image features  
6. Multimodal model training using XGBoost  
7. Interpretability analysis using Grad-CAM  
8. Final prediction and CSV generation  

---

## Exploratory Data Analysis (EDA)

Exploratory Data Analysis is performed to understand the distribution and relationships within the dataset. The house price distribution is right-skewed, indicating the presence of a small number of high-value properties.

Scatter plots between house price and numerical attributes such as living area and grade show strong positive correlations. However, significant variance is observed among houses with similar structural characteristics, suggesting the influence of neighborhood-level factors.

Visual inspection of sample satellite images reveals noticeable differences in greenery, road networks, and building density between high-priced and low-priced areas.

EDA visualizations and satellite image samples are included in the project notebooks.

---

## Model Performance Summary

### Tabular Data Only

Initial experiments are conducted using only tabular data to establish baseline performance.

- Linear Regression shows limited performance due to linear assumptions.
- Random Forest improves accuracy by modeling nonlinear feature interactions.
- **XGBoost performs best among tabular-only models**.

| Model | RMSE | R² Score |
|------|------|----------|
| Linear Regression | 0.248 | 0.707 |
| Random Forest | 0.178 | 0.866 |
| XGBoost | **0.162** | **0.905** |

### Tabular + Satellite Images (Multimodal)

The multimodal model combines tabular features with CNN-extracted image features.

| Model | MAE | R² Score |
|------|-----|----------|
| XGBoost (Fused) | **72,751** | **0.87** |

The multimodal model incorporates visual neighborhood context and provides competitive performance with improved interpretability.

---

## Interpretability and Visual Insights

Grad-CAM visualizations are used to interpret the CNN-based image features. The highlighted regions indicate that the model focuses on neighborhood layout, vegetation, road connectivity, and surrounding open spaces.

These visual insights align with real-world economic intuition, where properties located in greener and well-planned neighborhoods tend to have higher market value.

---

## Installation and Environment Setup

### Prerequisites

- Python 3.8 or higher  
- Jupyter Notebook or JupyterLab  

Name-Jampa Sri Pramodhitha
enrollment no.- 23113075






