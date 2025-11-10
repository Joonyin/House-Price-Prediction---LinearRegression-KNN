# House Price Prediction: Comparative Analysis of Linear Regression and k-Nearest Neighbors (kNN)

## Project Overview

This project aims to predict residential **house prices** using a dataset from the Kaggle House Prices - Advanced Regression Techniques competition. We compare the performance of two fundamental machine learning algorithms, **Linear Regression** and **k-Nearest Neighbors (kNN) Regression**, to determine the superior model for this specific prediction task.

The analysis focuses on standard regression evaluation metrics: **Root Mean Squared Error (RMSE)** and the **R-squared ($R^2$) score**, to provide a quantitative comparison of prediction accuracy and model fit.

---

## 🛠️ Project Workflow and Methodology

The project followed a standard machine learning pipeline:

### 1. Data Preprocessing and Feature Engineering
* **Loading and Imputation:** The raw dataset was loaded, and missing values were handled using simple imputation techniques.
* **Normalization:** Numerical features were scaled using `StandardScaler` to prevent features with larger magnitudes from dominating the model.
* **Encoding:** Categorical variables were converted into a numerical format using `OneHotEncoder`.
* **Feature Engineering:** New, informative features were created, such as calculating the **age of the house** from the `YearBuilt` feature.

### 2. Model Training and Hyperparameter Tuning
Two models were trained on the preprocessed data:

* **Linear Regression:** A parametric model chosen as a baseline, assuming a **linear relationship** between features and the target variable (SalePrice).
* **k-Nearest Neighbors (kNN) Regression:** A non-parametric model chosen to explore the benefit of a **local, distance-based** approach to prediction. Hyperparameters were optimized using **Grid Search**.

### 3. Model Evaluation
The models were evaluated on an unseen test set using the following metrics:

* **Root Mean Squared Error (RMSE):** Measures the average magnitude of the errors, representing the **square root of the average squared difference** between the predicted and actual values. Lower RMSE indicates better performance.
* **R-squared ($R^2$) Score:** Represents the **proportion of the variance** in the dependent variable that is predictable from the independent variables. A score closer to 1 indicates a better fit.

---

## Results and Performance Comparison

The following table summarizes the performance of both models on the test dataset:

| Model | RMSE | $R^2$ Score |
| :--- | :--- | :--- |
| **k-Nearest Neighbors (kNN)** | **35,308.64** | **0.82134** |
| Linear Regression | 42,645.12 | 0.73938 |

### Key Findings:

* **kNN Regression** demonstrated significantly **better performance**, achieving a **lower RMSE** (meaning more accurate predictions) and a **higher $R^2$ score** (meaning it explains a greater portion of the variance in house prices).
* The $R^2$ score of **0.82134** for kNN suggests the model explains over **82%** of the variability in the house prices.
* Linear Regression serves as a weak baseline, indicating that the relationship between the features and house price is likely **non-linear** or benefits from a localized, non-parametric approach.

### Optimized kNN Parameters:

The optimal configuration found via Grid Search for the kNN model was:
* **`n_neighbors`**: 9
* **`weights`**: 'distance' (neighbor points are weighted by the inverse of their distance)

---

## Conclusion

**kNN Regression outperforms Linear Regression** in this house price prediction task. The superior performance, evidenced by a **$17\%$ lower RMSE** and a **$11\%$ higher $R^2$ score** compared to the baseline, suggests that the underlying structure of the House Prices dataset is better captured by a non-linear, local-based algorithm. The kNN model is therefore better suited for providing accurate house price predictions using these features.

---

## Dataset Reference

The data used for this analysis is publicly available on Kaggle:

* **Dataset:** House Prices - Advanced Regression Techniques
* **Source:** [https://www.kaggle.com/c/house-prices-advanced-regression-techniques](https://www.kaggle.com/c/house-prices-advanced-regression-techniques)
