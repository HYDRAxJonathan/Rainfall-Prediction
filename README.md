# Rainfall Prediction 

## Introduction

Rainfall prediction is a crucial area of research in meteorology and agriculture. Accurate rainfall predictions aid in better planning and decision-making for activities such as crop cultivation, disaster management, and water resource management. This project utilizes AI and Machine Learning (ML) techniques to develop a precise and reliable rainfall prediction model using historical weather data.

## Project Overview

This project explores the use of AI/ML techniques in rainfall prediction by analyzing historical weather data from Australia. The primary objective is to create a model that can predict whether it will rain the next day (RainTomorrow) based on various weather parameters.

## Features

- **Increased Accuracy**: AI/ML models extract complex patterns and trends not apparent with traditional methods, leading to more accurate predictions.
- **Timely Forecasting**: AI/ML models process large datasets quickly, enabling timely rainfall forecasts.
- **Scalability**: The models can handle large datasets, making them scalable for different regions and time periods.
- **Cost-Effective**: The models require minimal physical infrastructure and can be implemented using cloud-based services.

## Dataset

The dataset used is the "Weather in Australia" dataset from Kaggle, which includes historical weather data from 2007 to 2017. The dataset comprises 1,45,460 records with 24 features.

**Key Features:**

- Date
- Location
- MinTemp
- MaxTemp
- Rainfall
- Evaporation
- Sunshine
- WindGustDir
- WindGustSpeed
- WindDir9am
- WindDir3pm
- WindSpeed9am
- WindSpeed3pm
- Humidity9am
- Humidity3pm
- Pressure9am
- Pressure3pm
- Cloud9am
- Cloud3pm
- Temp9am
- Temp3pm
- RainToday
- RainTomorrow (target variable)
- Dataset (train/test indicator)

## Model Creation

1. **Data Cleaning and Preprocessing**:
   - Handle missing values using random sample imputation.
   - Visualize data for outliers and distributions.
   - Encode target labels and normalize data.
   - Plot correlation heatmap.
   - Remove outliers and analyze data for the best fit line.

2. **Data Splitting**:
   - Split data into training and testing sets using `sklearn`'s `train_test_split`.

3. **Model Training**:
   - Use SMOTE for balanced data.
   - Select CatBoost classifier for its high accuracy (86%).
   - Evaluate model using accuracy score, confusion matrix, classification report, and ROC AUC score.

4. **Model Saving and Deployment**:
   - Save the model using `joblib`.
   - Deploy the model using Flask on Render.

## Results

| Method                 | Accuracy Score | ROC AUC Score |
|------------------------|----------------|----------------|
| CatBoost classifier    | 0.8640         | 0.7489         |
| Random forest classifier | 0.7565         | 0.8455         |
| Logistic regression    | 0.7648         | 0.7743         |
| Gaussian naïve bayes   | 0.7677         | 0.7538         |
| K-Neighbor classifier  | 0.7428         | 0.7538         |
| XGBoost classifier     | 0.7429         | 0.8562         |

## CatBoost Classifier

CatBoost is a supervised ML method using decision trees for classification and regression, particularly effective with categorical data and gradient boosting. The process includes:

1. **Data Preprocessing**: Feature selection, data cleaning, and normalization.
2. **Initialization**: Starts with a single decision tree predicting the mean target value.
3. **Gradient Boosting**: Trains multiple decision trees sequentially, correcting previous errors.
4. **Tree Generation**: Selects best split points by minimizing the loss function.
5. **Shrinkage**: Reduces the weight of new trees to prevent overfitting.
6. **Prediction**: Uses the majority vote of decision trees for final prediction.

## Deployment

The model is deployed using Flask on Render.

## Usage

To use this project:

1. **Clone the repository**:
   ```sh
   git clone https://github.com/yourusername/rainfall-prediction.git
   cd rainfall-prediction
