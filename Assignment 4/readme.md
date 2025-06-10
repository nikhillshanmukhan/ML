# Breast Cancer Classification: Model Implementation and Evaluation

## 1. Loading and Preprocessing

### Loading the Dataset
The breast cancer dataset is loaded from `sklearn.datasets` using `load_breast_cancer()`.

### Preprocessing Steps
- **Missing Values**:
  - The dataset was checked for missing values, and none were found
  - No imputation was necessary

- **Feature Scaling**:
  - All features were scaled using `StandardScaler` to ensure zero mean and unit variance
  - Crucial for algorithms like Logistic Regression, SVM, and k-NN to perform optimally

### Justification
Scaling is especially important for:
- Distance-based classifiers (k-NN, SVM)
- Regularization-based classifiers (Logistic Regression)
Unscaled features can bias the model toward features with larger ranges.

## 2. Classification Algorithm Implementation

| Algorithm | Description | Suitability |
|-----------|------------|-------------|
| **Logistic Regression** | Linear model estimating probabilities using a logistic function | Good for binary classification, interpretable, works well with scaled data |
| **Decision Tree** | Splits data based on feature values to form a tree structure | Captures non-linear relationships, easy to interpret, but can overfit |
| **Random Forest** | Ensemble of decision trees; averages results to improve accuracy | Handles complex data well, robust to overfitting |
| **SVM** | Finds the hyperplane that best separates classes | Effective in high-dimensional spaces, sensitive to feature scaling |
| **k-NN** | Classifies based on majority class among k nearest neighbors | Simple, effective for small/medium datasets, performance depends on scaling |

All five algorithms were implemented using sklearn's built-in classifiers.

## 3. Model Comparison

**Performance Results (Accuracy on Test Set):**

| Algorithm | Accuracy |
|-----------|----------|
| Logistic Regression | 0.982 |
| Decision Tree | 0.942 |
| Random Forest | 0.971 |
| SVM | 0.971 |
| k-NN | 0.959 |

- **Best Performing**: Logistic Regression (accuracy: 0.982)
- **Worst Performing**: Decision Tree (accuracy: 0.942)
