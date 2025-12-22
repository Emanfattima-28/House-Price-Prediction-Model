# House-Price-Prediction-Model
# Problem Statement

Housing prices depend on several factors such as location, size, condition, number of rooms, and available facilities. Accurately predicting house prices is important for buyers, sellers, and real estate companies.
The goal of this project is to analyze housing data, engineer meaningful features, and build a machine learning model that can predict house prices using Random Forest Regression.

# Dataset Description
Dataset Name: House Price Dataset
Target Variable: Price
Rows: Varies based on dataset
Type: Structured tabular data

# Key Features:
Area – Size of the house
Bedrooms – Number of bedrooms
Bathrooms – Number of bathrooms
Floors – Number of floors
YearBuilt – Year of construction
Location – Area type (Suburban, Downtown, Urban, Rural)
Condition – House condition (Poor, Fair, Good, Excellent)
Garage – Availability of garage

# Tools & Libraries Used
Python
NumPy & Pandas – Data preprocessing and analysis
Matplotlib & Seaborn – Data visualization
Scikit-learn – Feature encoding, scaling, modeling, and evaluation

# Project Workflow & Explanation
# 1.Data Loading & Cleaning
> Dataset loaded using Pandas.
> Id column removed as it does not contribute to prediction.
> Dataset inspected using info(), describe(), and shape analysis.
> Checked for missing values and duplicate records.

# 2.Exploratory Data Analysis (EDA)
> The following visualizations were created to understand data patterns:
> Price Distribution using histogram with KDE
> Area Distribution
> Bathrooms Distribution
> Correlation Heatmap to identify relationships among numeric features
> Boxplots showing the effect of:
  Location on Price
  Condition on Price
  Garage availability on Price

# 3.Outlier Detection
> Outliers in Price were detected using the Interquartile Range (IQR) method.
> The number of extreme price values was identified for better understanding of data spread.

# 4.Feature Engineering
> New meaningful features were created:
> Log_SalePrice – Log transformation of price to reduce skewness
> TotalRooms – Sum of bedrooms and bathrooms
> HouseAge – Calculated from year built
> IsMultiFloor – Binary indicator for multi-floor houses

# 5.Feature Scaling
Numerical features (Area, TotalRooms, HouseAge) were scaled using StandardScaler to improve model performance.

# 6.Encoding Categorical Variables
Garage: Label encoded (Yes → 1, No → 0)
Condition: Ordinal encoding based on quality order
Location: Ordinal encoding based on development level

# 7.Train-Test Split

Dataset split into 80% training and 20% testing sets.

Target variable used: Log_SalePrice.

# 8.Model Building
> A Random Forest Regressor was trained to predict house prices.
> Initial model evaluation was done using:
  R² Score
  Mean Absolute Error (MAE)
  Mean Squared Error (MSE)
  Root Mean Squared Error (RMSE)

# 9.Hyperparameter Tuning
> GridSearchCV was applied to optimize:
  Number of trees
  Tree depth
  Minimum samples for split and leaf
  Feature selection strategy

The best-performing model was selected and evaluated again.

# Model Evaluation Metrics
R² Score: Measures how well the model explains price variance
MAE: Average absolute prediction error
RMSE: Penalizes large prediction errors

The tuned Random Forest model showed improved performance compared to the baseline model.

# Key Insights
> Location and condition have a strong impact on house prices.
> Larger area and newer houses tend to have higher prices.
> Log transformation of price improves prediction stability.
> Feature engineering significantly enhances model accuracy.
> Random Forest performs well for non-linear housing data.

# Conclusion
This project successfully demonstrates how exploratory data analysis, feature engineering, and ensemble machine learning models can be used to predict house prices effectively.
The Random Forest Regressor, combined with proper preprocessing and hyperparameter tuning, provides reliable predictions and handles complex feature interactions well.
