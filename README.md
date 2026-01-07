Multimodal House Price Prediction Using Tabular Data and Satellite Imagery
Project Overview

This project focuses on predicting residential house prices using a multimodal machine learning approach that combines structured tabular data with satellite imagery. Traditional house price prediction models rely mainly on numerical property attributes, which often fail to capture neighborhood-level and environmental factors. To overcome this limitation, satellite images are incorporated to provide additional spatial and contextual information.

The project demonstrates how convolutional neural networks (CNNs) can be used to extract meaningful visual features from satellite images and how these features can be fused with tabular data to improve prediction robustness and interpretability.

Dataset Description

The dataset consists of two components:

Tabular Data:
Contains house-level attributes such as living area, number of bedrooms, number of bathrooms, construction year, renovation year, and geographic coordinates.

Satellite Images:
Satellite images are downloaded using latitude and longitude values via the Mapbox Static Images API. These images capture neighborhood characteristics such as greenery, road connectivity, and building density.

The training dataset includes house prices as the target variable, while the test dataset contains only input features.

Methodology

The project is implemented in the following stages:

Satellite Image Collection
Satellite images are downloaded for each house location using the Mapbox API and stored locally for reuse.

Data Preprocessing
Tabular data is cleaned, irrelevant features are removed, missing values are handled, and numerical features are scaled.

Baseline Modeling (Tabular Only)
Multiple regression models are trained using only tabular data to establish baseline performance.

Image Feature Extraction
A pretrained ResNet50 convolutional neural network is used to extract high-level visual features from satellite images.

Feature Fusion
Tabular features and image features are concatenated to form a multimodal feature representation.

Multimodal Model Training
An XGBoost regression model is trained on the fused feature set.

Interpretability
Grad-CAM visualizations are generated to interpret which regions of satellite images influence the learned visual representations.

Final Prediction
The trained multimodal model is applied to the test dataset and predictions are exported as a CSV file.

Exploratory Data Analysis (EDA)

Exploratory Data Analysis shows that house prices are right-skewed, with a small number of high-value properties. Scatter plots reveal strong correlations between price and features such as living area and house grade, while also highlighting significant variance among houses with similar structural attributes.

Sample satellite images reveal clear visual differences between neighborhoods, including variations in greenery, road density, and surrounding infrastructure. These observations motivate the inclusion of image-based features in the model.

Model Performance Summary
Tabular Data Only

Linear Regression shows limited performance due to linear assumptions.

Random Forest improves accuracy by capturing nonlinear relationships.

XGBoost (Best Tabular Model):

Validation RMSE ≈ 0.162

R² Score ≈ 0.905

Tabular + Satellite Images (Multimodal)

XGBoost (Fused Features):

Mean Absolute Error (MAE) ≈ 72,751

R² Score ≈ 0.87

The multimodal model provides competitive performance and improved interpretability by incorporating neighborhood-level visual context.

Interpretability and Insights

Grad-CAM visualizations indicate that the CNN focuses on neighborhood layout, road connectivity, vegetation, and surrounding open spaces when extracting visual features. This confirms that satellite imagery captures meaningful environmental cues that influence house prices.

Repository Structure and File Description
File Name	Description
DATA_FETCHER.ipynb	Downloads satellite images using latitude and longitude via the Mapbox Static Images API.
01_preprocessing (2) (1).ipynb	Cleans and preprocesses tabular housing data.
02_Model_Training_Baseline (2).ipynb	Trains and evaluates baseline models using only tabular data.
04_Image_Feature_Extraction.ipynb	Extracts image features using ResNet50 and performs multimodal feature fusion.
Prediction file download.ipynb	Loads the trained multimodal model and generates test predictions.
23113075.csv	Final submission file containing predicted house prices.
README.md	Project documentation and usage instructions.
Conclusion

This project demonstrates the effectiveness of a multimodal machine learning framework for house price prediction. While tabular features provide strong predictive power, satellite imagery contributes valuable neighborhood-level context and improves interpretability. The approach highlights the potential of combining structured and unstructured data sources for real-world regression problems.

Author

Enrollment Number: 23113075
Project Type: Multimodal Machine Learning
Techniques Used: Regression, CNN Feature Extraction, Feature Fusion, XGBoost

