# California House Price Predictor (Linear Regression Model for House Price Prediction)

## Project Objective

The goal of this project is to build an accurate and interpretable Linear Regression model to predict median house prices across California neighborhoods, helping real estate analysts, investors, and policymakers make data-driven decisions. The model enables price estimation by learning patterns from demographic and geographic features of housing blocks across California.

##  Dataset Used
- <a href="https://github.com/suriya2318/California-House-Price-Predictor/blob/main/California_Housing%20Datasets.csv"> California_Housing Dataset</a>

## Key Business Questions (KPIs)
•	What is the average median house price across California neighborhoods?

•	Which features have the strongest influence on house prices?

•	How accurately can a linear model predict house prices on unseen data?

•	What is the average prediction error in dollar terms (MAE)?

•	How much of the price variation does the model explain (R² Score)?

•	Which neighborhoods are consistently over-predicted or under-predicted?

•	Is there a correlation between median income and house price?

•	How does geographic location (latitude/longitude) affect house prices?

•	What improvements can be made to increase model accuracy beyond 66%?

## Process
### 1. Data Loading & Exploration
• Loaded the California Housing Dataset using sklearn.datasets.fetch_california_housing.

• Verified all 20,640 rows — confirmed zero missing values across all 8 features.

• Explored statistical distributions using df.describe() and df.info().

### 2. Exploratory Data Analysis (EDA)
• Plotted distribution histograms for all 9 features (8 inputs + 1 target).

• Generated a correlation heatmap to identify relationships between features and the target.

• Discovered that MedInc has the highest positive correlation (~0.69) with house price.

• Identified that AveOccup and Population have weak negative correlations with price.

### 3. Data Preprocessing
• Applied StandardScaler to normalize all 8 input features to the same scale.

• Split the dataset into 80% training (16,512 rows) and 20% testing (4,128 rows) using train_test_split with random_state=42.

### 4. Model Training
• Trained a LinearRegression model from sklearn.linear_model on the scaled training data.

• Extracted and analyzed feature coefficients to understand the weight of each feature.

### 5. Model Evaluation
• Evaluated the model using three standard regression metrics: MAE, RMSE, and R².

• Plotted Actual vs. Predicted scatter chart to visually assess prediction quality.

• Plotted Residual chart to check for patterns in prediction errors.

### 6. Visualization & Reporting
• Built 5 charts: Feature Distributions, Correlation Heatmap, Actual vs. Predicted, Residual Plot, and Feature Coefficients.

• Delivered a full structured PDF report covering all 8 sections from Introduction to Conclusion.

• Saved the trained model using pickle for future inference.

## Charts & Visualizations Overview

### Chart 1: Feature Distributions (Histogram Grid)
• Displays the frequency distribution of all 9 features across 20,640 housing blocks.

• Reveals right-skewed distributions for MedInc and Population indicating outliers.

• Helps identify the data shape before model training.

### Chart 2: Correlation Heatmap
• Shows pairwise correlation between all features and the target variable.

• Confirms MedInc as the strongest predictor of house price (r ≈ 0.69).

• Highlights negative correlation of AveOccup with price.

### Chart 3: Actual vs. Predicted Scatter Plot
• Compares the model's predictions against real house prices on the test set.

• A perfect model would place all dots on the red dashed diagonal line.

• Shows the model performs well for low-to-mid priced homes but under-predicts expensive ones.

### Chart 4: Residual Plot
• Plots the difference between actual and predicted values against predicted values.

• Ideal residuals scatter randomly around zero — patterns indicate missed non-linearity.

• Our model shows slight under-prediction at higher price ranges.

### Chart 5: Feature Coefficients Bar Chart
• Visualizes the impact and direction of each feature on the predicted house price.

• MedInc has the largest positive coefficient — income drives price most strongly.

• AveOccup has a notable negative coefficient — overcrowded blocks cost less.
