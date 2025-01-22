# Telecommunications Customer Churn Prediction

**Overview**

This project focuses on predicting customer churn for a telecommunications company using statistical learning and machine learning techniques. The dataset comprises customer demographic information, service usage patterns, and contract details. The primary goal is to identify customers likely to churn, enabling targeted retention strategies.

**Dataset**
  * **Source:** Kaggle - Telecommunications Customer Churn Dataset
  * **Size:** 7043 rows and 21 columns
  * **Key Features:**
      * **Categorical:** Gender, Contract Type, Internet Service, etc.
      * **Numerical:** Tenure, Monthly Charges, Total Charges
      * **Target Variable:** Churn (Yes/No)
        
**Objective**

  * Predict whether a customer will churn using predictive modeling techniques.
  * Identify the most impactful factors influencing churn.
    
**Methodology**

1.**Data Preprocessing:**

  * Handled missing values using median imputation.
  * Addressed class imbalance using stratified sampling.
  * Transformed and encoded categorical variables (one-hot encoding).
  * Feature engineering:
    * Created new features (e.g., ServiceCount, tenure bins).
    * Removed highly correlated and low-variance features.
      
2.**Exploratory Data Analysis:**

  * Analyzed distribution and relationships among features.
  * Visualized numerical data (histograms, boxplots, correlation heatmaps).
  * Evaluated categorical data interactions with churn using bar charts and chi-square tests.

3.**Statistical Learning Models:**

  * Baseline model: Logistic Regression
  * Advanced models: Random Forest, XGBoost
  * Hyperparameter tuning applied to optimize performance.
    
4.**Model Evaluation:**

  * Metrics used: Accuracy, Precision, Recall, F1-score, ROC-AUC.
  * Resampling techniques: Cross-validation for robust evaluation.


**Results**

  * Best Model: Logistic Regression
    * **ROC-AUC:** 0.8441
    * **F1-Score:** 0.872
    * High recall ensures effective identification of churners.
    * Chosen for its simplicity, interpretability, and consistent performance across validation and test datasets.
      
  * Other Models:
    * **XGBoost:** High ROC-AUC (0.8391) but lower recall.
    * **Random Forest:** Performance improved with fine-tuning but remained less effective than Logistic Regression.
      
**Technologies Used**

  * **Programming Language:** R
  * **Libraries:** ggplot2, caret, randomForest, xgboost, pROC, corrplot
  * **Tools:** RStudio
    
**Key Insights**

  * Features like tenure, contract type, and payment methods are strong predictors of churn.
  * Customers on monthly contracts, paying via electronic checks, and using fiber optic internet are more likely to churn.
    
**Limitations**

  * Logistic Regression assumes linear relationships, limiting its ability to model non-linear patterns.
  * Handling class imbalance could further improve precision.
  * Ensemble models (e.g., Random Forest, XGBoost) may perform better with optimized hyperparameter tuning.

**Future Improvements**

  * Implement advanced feature engineering (e.g., interaction terms, polynomial features).
  * Explore techniques like SMOTE for better handling of class imbalance.
  * Enhance model performance with deeper hyperparameter optimization for ensemble methods.

**Conclusion**
This project demonstrates a practical approach to customer churn prediction using machine learning, emphasizing interpretability and actionable insights. The Logistic Regression model effectively balances simplicity, performance, and interpretability, making it an ideal solution for this use case.
