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

### Chart 1: Feature Distributions
• Displays the frequency distribution of all 9 features across 20,640 housing blocks.

• Reveals right-skewed distributions for MedInc and Population indicating outliers.

• Helps identify the data shape before model training.

 ![Feature Distributions](https://github.com/suriya2318/California-House-Price-Predictor/blob/main/Feature%20Distributions.png)

### Chart 2: Correlation
• Shows pairwise correlation between all features and the target variable.

• Confirms MedInc as the strongest predictor of house price (r ≈ 0.69).

• Highlights negative correlation of AveOccup with price.

![Correlation](https://github.com/suriya2318/California-House-Price-Predictor/blob/main/correlation.png)

### Chart 3: Actual vs. Predicted
• Compares the model's predictions against real house prices on the test set.

• A perfect model would place all dots on the red dashed diagonal line.

• Shows the model performs well for low-to-mid priced homes but under-predicts expensive ones.

![Actual vs. Predicted](https://github.com/suriya2318/California-House-Price-Predictor/blob/main/actual_vs_predicted.png)

### Chart 4: Residual
• Plots the difference between actual and predicted values against predicted values.

• Ideal residuals scatter randomly around zero — patterns indicate missed non-linearity.

• Our model shows slight under-prediction at higher price ranges.

![Residual](https://github.com/suriya2318/California-House-Price-Predictor/blob/main/residuals.png)

### Chart 5: Feature Coefficients
• Visualizes the impact and direction of each feature on the predicted house price.

• MedInc has the largest positive coefficient — income drives price most strongly.

• AveOccup has a notable negative coefficient — overcrowded blocks cost less.

![Feature Coefficients](https://github.com/suriya2318/California-House-Price-Predictor/blob/main/correlation.png)

## Project Insights

• MedInc is the single strongest predictor of house prices — higher income neighborhoods are consistently more expensive.
• A direct positive relationship exists between geographic location and house price — coastal California neighborhoods command significantly higher prices.
• AveOccup has a negative effect on price — blocks with more people per household tend to have lower median house values.
• The model predicts low-to-mid priced homes well but underestimates very expensive properties, a known limitation of linear models.
• Zero missing values were found in the dataset — no imputation was required, confirming high data quality.
• Feature scaling with StandardScaler was critical — without it, features with larger numerical ranges (like Population) would dominate the model unfairly.
• An R² of 0.666 confirms that 66.6% of price variation is explained by the 8 features, leaving room for non-linear models to capture the remaining 33.4%.
• The residual plot reveals mild heteroscedasticity at higher price ranges, suggesting that non-linear algorithms like Random Forest or XGBoost would reduce prediction errors significantly.

## Final Conclusion
This California House Price Predictor project successfully demonstrates the complete Machine Learning lifecycle — from raw data loading and exploratory analysis through preprocessing, model training, evaluation, and professional reporting. The Linear Regression model achieved an R² score of 0.666, a MAE of 0.5861 ($58,610 average error), and an RMSE of 0.7539 on the test set, representing a solid baseline performance for a linear model. By investing in advanced techniques such as Ridge/Lasso regularization, polynomial feature engineering, and tree-based models like Random Forest or Gradient Boosting, prediction accuracy can be improved to R² scores of 0.85 and above. This project provides a strong, reproducible foundation for building more sophisticated house price prediction systems and demonstrates core data science competencies including EDA, feature engineering, model evaluation, and data storytelling through visualization.

