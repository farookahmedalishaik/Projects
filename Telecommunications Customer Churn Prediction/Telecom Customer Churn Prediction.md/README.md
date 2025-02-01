# Customer Churn Prediction Project

## Overview

This project focuses on predicting customer churn for a telecommunications company using both statistical learning and machine learning techniques. The main objective is to identify customers who are likely to churn so that targeted retention strategies can be implemented. This document provides a step-by-step explanation of the methods, techniques, and decisions made throughout the project.

---

## Dataset

**Source:** Kaggle - Telecommunications Customer Churn Dataset  
**Size:** 7,043 rows and 21 columns  

**Key Features:**

- **Categorical Variables:**  
  - *Gender*
  - *Contract Type*
  - *Internet Service*
  - *Payment Method*
  - *Other service-related features*

- **Numerical Variables:**  
  - *Tenure* (number of months as a customer)
  - *Monthly Charges*
  - *Total Charges*

- **Target Variable:**  
  - *Churn* (Yes/No)

---

## Objective

- **Predictive Modeling:** Develop models to predict whether a customer will churn.
- **Feature Impact:** Identify the most influential factors (e.g., tenure, contract type, payment method) contributing to customer churn.
- **Actionable Insights:** Enable the telecommunications company to design targeted customer retention strategies.

---

## Methodology

### 1. Data Preprocessing

**a. Handling Missing Values:**

- **Method:** Median Imputation  
  - Missing numerical values were replaced with the median value of the corresponding feature.
  - *Reasoning:* The median is less sensitive to outliers compared to the mean.

**b. Addressing Class Imbalance:**

- **Method:** Stratified Sampling  
  - Ensured that the train and test splits maintained the same proportion of churn classes.
  - *Reasoning:* This preserves the distribution of the target variable, leading to more reliable model evaluation.

**c. Data Transformation and Encoding:**

- **Categorical Variables:**
  - Applied one-hot encoding to transform categorical features into binary indicator variables.
  - *Detail:* This process creates new columns for each category level, allowing algorithms to interpret these non-numeric inputs.
  
- **Feature Engineering:**
  - **New Features:**
    - *ServiceCount:* Aggregated count of services a customer subscribes to.
    - *Tenure Bins:* Categorized customers based on their tenure (e.g., 0-12 months, 13-24 months, etc.).
  - **Feature Reduction:**
    - Removed features that were highly correlated with each other to reduce redundancy.
    - Dropped low-variance features that did not contribute much to the predictive power of the model.

---

### 2. Exploratory Data Analysis (EDA)

**a. Univariate Analysis:**

- **Numerical Data:**  
  - Created histograms and boxplots to understand the distribution and spread of features like *Tenure*, *Monthly Charges*, and *Total Charges*.
- **Categorical Data:**  
  - Used bar charts to visualize the frequency of categories (e.g., Contract Types, Payment Methods).

**b. Bivariate and Multivariate Analysis:**

- **Correlation Analysis:**
  - Generated correlation heatmaps to identify relationships between numerical variables.
- **Chi-Square Tests:**
  - Conducted chi-square tests to examine the association between categorical variables and the target variable (*Churn*).

---

### 3. Modeling

**a. Statistical Learning Models:**

- **Baseline Model: Logistic Regression**
  - *Usage:* Provided an interpretable baseline to compare against more complex models.
  - *Feature Selection:* Incorporated key predictors identified during EDA and feature engineering.
  - *Performance Metrics:* Achieved a ROC-AUC of 0.8441 and an F1-score of 0.872.
  
**b. Advanced Machine Learning Models:**

- **Random Forest:**
  - *Implementation:* Tuned hyperparameters (e.g., number of trees, maximum depth) to improve performance.
  - *Observation:* While performance improved with fine-tuning, it did not surpass the logistic regression baseline.
  
- **XGBoost:**
  - *Implementation:* Applied gradient boosting techniques with hyperparameter optimization.
  - *Observation:* Recorded a high ROC-AUC (0.8391), but overall recall was lower compared to logistic regression.

**c. Hyperparameter Tuning:**

- **Technique:** Cross-Validation  
  - Performed grid search and cross-validation to find the optimal set of hyperparameters for each model.
  - *Goal:* Ensure robust evaluation and prevent overfitting.

---

### 4. Model Evaluation

**Metrics Used:**

- **Accuracy:** Overall correctness of the model predictions.
- **Precision:** The ratio of correctly predicted churners to all predicted churners.
- **Recall:** The ability of the model to identify actual churners.
- **F1-Score:** Harmonic mean of precision and recall, providing a balance between the two.
- **ROC-AUC:** Measures the model’s ability to distinguish between classes across different thresholds.

**Resampling Technique:**

- **Cross-Validation:**
  - Used to ensure the model’s stability and generalizability.
  - *Reasoning:* Helps in assessing performance across different subsets of the data.

---

## Results

- **Best Model:** Logistic Regression  
  - **Performance:**  
    - *ROC-AUC:* 0.8441  
    - *F1-Score:* 0.872  
  - **Strengths:**  
    - High recall ensures effective identification of churners.
    - Model simplicity and interpretability make it ideal for deriving actionable insights.

- **Other Models:**
  - **XGBoost:** Achieved a comparable ROC-AUC but with lower recall.
  - **Random Forest:** Showed potential improvements through tuning but did not outperform logistic regression.

---

## Key Insights

- **Predictors of Churn:**  
  - *Tenure:* Shorter tenure customers are more likely to churn.
  - *Contract Type:* Customers with monthly contracts have a higher risk of churning.
  - *Payment Method:* Electronic check payments are linked with higher churn rates.
  - *Internet Service:* Customers using fiber optic internet also showed increased churn tendencies.

---

## Limitations

- **Model Assumptions:**
  - Logistic regression assumes a linear relationship between predictors and the log-odds of the outcome, which may limit its ability to capture non-linear patterns.
  
- **Handling Class Imbalance:**
  - While stratified sampling was used, further techniques (e.g., SMOTE) could potentially improve precision and overall model performance.
  
- **Feature Engineering:**
  - Some engineered features may require further validation to ensure they contribute positively to model performance.

---

## Future Improvements

- **Advanced Feature Engineering:**
  - Consider incorporating interaction terms and polynomial features to capture non-linear effects.
  
- **Enhanced Imbalance Handling:**
  - Experiment with methods such as SMOTE (Synthetic Minority Over-sampling Technique) to better address class imbalance.
  
- **Deeper Hyperparameter Optimization:**
  - Further refine ensemble models (Random Forest, XGBoost) using more exhaustive search techniques to maximize predictive performance.
  
- **Integration of Additional Data:**
  - Include more granular customer data or external data sources to enrich the model.

---

## Conclusion

This project demonstrates a comprehensive approach to customer churn prediction using machine learning. The use of logistic regression as the baseline model provided clear, interpretable insights, while advanced models like Random Forest and XGBoost were also explored for potential improvements. Although logistic regression emerged as the best performing model based on ROC-AUC and F1-score, there remains ample opportunity for further refinement through enhanced feature engineering, improved handling of class imbalance, and deeper hyperparameter tuning.

By following this detailed process, the project not only predicts customer churn effectively but also offers actionable insights that can be leveraged for targeted customer retention strategies.

---

*End of Document*
