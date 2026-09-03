# California Housing Price Prediction 🏡

## Project Overview
This project aims to predict the median house values in Californian districts using Machine Learning techniques. The dataset contains various features such as population, median income, and geographical locations. I built and optimized a regression model to understand the underlying patterns and make accurate price predictions on unseen data.

## Data Preprocessing & Feature Engineering
To prepare the raw data for the machine learning model, the following preprocessing steps were applied:
* **Handling Missing Values:** Dropped rows with missing values to maintain data integrity.
* **Log Transformation:** Applied logarithmic transformations to skewed numerical features (e.g., `total_rooms`, `total_bedrooms`, `population`, `households`) to normalize their distribution and handle outliers.
* **Feature Engineering:** Created two new meaningful features to help the model learn better:
  * `bedroom_ratio`: Ratio of total bedrooms to total rooms.
  * `household_rooms`: Average rooms per household.
* **One-Hot Encoding:** Converted the categorical variable `ocean_proximity` into dummy variables and aligned training/testing columns to prevent data leakage.
* **Feature Scaling:** Used `StandardScaler` to standardize features before feeding them to the models.

## Modeling Approach
1. **Linear Regression:** Started with a baseline Multiple Linear Regression model to establish initial performance.
2. **Random Forest Regressor:** Transitioned to an ensemble learning approach using `RandomForestRegressor` to capture complex, non-linear relationships in the data.

## Hyperparameter Tuning
To achieve the best possible performance, I used `GridSearchCV` with 5-fold Cross-Validation. The model was fine-tuned over the following parameters:
* `n_estimators`: [3, 10, 30]
* `max_features`: [2, 4, 6, 8]

## Final Evaluation & Results
The models were evaluated using the R² (R-squared) score on the **unseen test dataset**. Moving from a simple linear model to an advanced Random Forest yielded significant improvements:
* **Linear Regression R² Score:** 67.67%
* **Random Forest R² Score (Base Model):** 81.82%
* **Optimized Random Forest R² Score (Test Data):** 81.60%

## Technologies Used
* Python
* Pandas & NumPy (Data Manipulation)
* Scikit-Learn (Machine Learning & Preprocessing)
* Matplotlib & Seaborn (Data Visualization)
