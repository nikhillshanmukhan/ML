# Car Price Prediction Analysis

## 1. Loading and Preprocessing
The car price dataset was loaded and checked for missing values; none were found. The features were split into numerical and categorical columns. Preprocessing included:

- Imputing missing values (median for numerical, most frequent for categorical)
- Scaling numerical features
- One-hot encoding categorical variables
- Splitting data into training (80%) and test (20%) sets

The processed training data had 164 samples and 51 features; the test set had 41 samples and 51 features.

## 2. Model Implementation
Five regression models were implemented:

1. Linear Regression
2. Decision Tree Regressor
3. Random Forest Regressor
4. Gradient Boosting Regressor
5. Support Vector Regressor (SVR)

All models were trained on the preprocessed training data.

## 3. Model Evaluation
The models were evaluated on the test set using R-squared (R²), Mean Squared Error (MSE), and Mean Absolute Error (MAE):

| Model                  | R²     | MSE        | MAE     |
|------------------------|--------|------------|---------|
| Linear Regression      | 0.872  | 10,067,307 | 2,244.60 |
| Decision Tree          | 0.896  | 8,223,687  | 1,847.43 |
| Random Forest          | 0.958  | 3,337,152  | 1,276.40 |
| Gradient Boosting      | 0.927  | 5,786,643  | 1,666.40 |
| Support Vector Regressor | -0.100 | 86,811,855 | 5,694.47 |

**Best Model:**  
The Random Forest Regressor outperformed all others with:
- Highest R² (0.958)
- Lowest MSE (3,337,152)
- Lowest MAE (1,276.40)

## 4. Feature Importance Analysis
Feature importance from the Random Forest model identified the most significant variables affecting car price:

1. `enginesize`
2. `curbweight`
3. `highwaympg`
4. `horsepower`

These features had importances above the mean importance threshold. Other notable features included:
- carwidth
- carlength
- wheelbase
- peakrpm
- citympg
- stroke

## 5. Hyperparameter Tuning
Hyperparameter tuning was performed on the Random Forest Regressor. The best model had:

- `n_estimators`: 200
- `max_depth`: None
- `min_samples_split`: 2
- `min_samples_leaf`: 1

Performance after tuning:
- R²: 0.958 (slight improvement)
- MSE: 3,278,678.98 (improved)
- MAE: 1,254.70 (improved)

## Summary Table

| Step                     | Key Findings |
|--------------------------|--------------|
| Preprocessing            | No missing values, 51 features after encoding |
| Best Model               | Random Forest Regressor (R² = 0.958, lowest MSE and MAE) |
| Significant Variables    | enginesize, curbweight, highwaympg, horsepower |
| Hyperparameter Tuning    | Slight performance improvement with 200 trees, no depth limit, min_samples_split=2, min_leaf=1 |

## Business Insights
- Car price in the US market is most strongly influenced by engine size, curb weight, highway fuel efficiency, and horsepower
- Random Forest models provide robust, interpretable predictions for car pricing
- Fine-tuning the model's parameters can yield marginal gains in predictive accuracy
