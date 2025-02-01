# Optimizing Resource Utilization on the Cori Supercomputer

## Overview

This project analyzes resource utilization patterns on the NERSC Cori supercomputer, focusing on optimizing computational efficiency through advanced data analysis and machine learning techniques. The analysis encompasses workload patterns, power consumption prediction, and resource optimization strategies.

---

## Dataset Description

* **Size:** 4,401 observations across 14 features  
* **Time Period:** One week of operations in 2020

### Key Variables

* **Categorical:** `exename`, `appname`
* **Temporal:** `start`, `end`
* **Numerical:** `jobid`, `numnodes`, `numcpus`, `numtasks`, `executiontime`, `power`, `memory`, `taskspercpu`, `taskspernode`, `user`

---

## Technical Implementation

* **Primary Language:** R (version 4.3.3)

### Key Libraries

* **Data Processing:** `tidyverse`, `lubridate`
* **Visualization:** `ggplot2`, `plotly`, `corrplot`, `cowplot`
* **Machine Learning:** `caret`, `randomForest`
* **Metrics:** `Metrics`, `broom`
* **Statistical Analysis:** `rsample`

---

## Data Preparation Methodology

### Data Cleaning

* Handling missing values through NA omission  
* Converting categorical variables (`exename`, `appname`) to factors  
* Normalizing data types across variables  
* Validating data consistency and integrity

### Feature Engineering

* Created temporal features (`hour`, `day_of_week`) from timestamps  
* Developed utilization metrics (`cpu_utilization`, `memory_utilization`)  
* Normalized execution times and resource usage metrics

### Data Splitting

* **Training set:** 60% (2,640 observations)  
* **Validation set:** 20% (880 observations)  
* **Test set:** 20% (881 observations)

---

## Analysis Components

### 1. Workload Pattern Analysis

#### Temporal Analysis

* Created daily execution time aggregations  
* Generated hourly utilization heatmaps  
* Identified peak usage periods (6 AM - 7 PM weekdays)

#### Key Findings

* Higher computational loads during weekdays  
* Consistent weekly patterns in resource utilization  
* Clear business hour peaks in system usage

### 2. Application Resource Impact Analysis

#### Resource Metrics

* **Average Execution Time per Application**  
* **Power Consumption Patterns**  
* **Memory Utilization Trends**  
* **Computational Load Distribution**

#### High-Resource Applications Identified

* **Power Consumption:** `chroma`, `gene`, `qlua`, `vasp`, `su3`  
* **Execution Time:** `chroma`, `gene`, `qlua`, `vasp`  
* **Memory Usage:** `chroma`, `qlua`, `vasp`, `wrf`  
* **Computational Load:** `chroma`, `qlua`, `vasp`, `cmip5`, `e3sm`

### 3. Predictive Modeling for Power Usage

#### Linear Regression Model

* **Mean Cross-Validated RMSE:** 35.56  
* **MSE:** 1,207.90  
* **RMSE:** 34.75  
* **MAE:** 28.44

#### Polynomial Regression Model

* **Mean Cross-Validated RMSE:** 32.84  
* **MSE:** 988.49  
* **RMSE:** 31.44  
* **MAE:** 24.29

#### Random Forest Model (Best Performing)

* **Mean Cross-Validated RMSE:** 11.82  
* **MSE:** 140.66  
* **RMSE:** 11.86  
* **MAE:** 6.67

### 4. Correlation Analysis

* **Strong Correlations (>0.7):**
  * `taskspernode` & `taskspercpu`
* **Moderate Correlations (0.4-0.7):**
  * `power` & `memory`
  * `numnodes` & `numtasks`
* **Weak Correlations (<0.4):**
  * `numnodes` & `executiontime`
  * `executiontime` & `power`

### 5. Resource Utilization Optimization

#### High Utilization Periods Identified

* December 1st (early hours)  
* December 3rd (mid-day)  
* December 5th (mid-day and evening)  
* December 6th (mid-day and evening)  
* December 7th (early hours)

#### Optimization Strategies

* **Application-Level Optimization:**
  * Code optimization for high-resource applications  
  * Algorithm improvements for resource-intensive tasks  
  * Evaluation of alternative computational approaches

* **Resource Allocation:**
  * Dedicated resource pools for high-demand applications  
  * Dynamic scheduling based on utilization patterns  
  * Workload distribution optimization

* **Load Balancing:**
  * Cross-node workload distribution  
  * Resource contention minimization  
  * Peak usage period management

* **Capacity Planning:**
  * Hardware upgrade recommendations  
  * Resource allocation policy updates  
  * System scaling strategies

---

## Limitations and Future Work

### Current Limitations

* **Dataset Constraints:**
  * Single week of data limits long-term pattern analysis  
  * Potential seasonal variations not captured  
  * Limited application diversity in sample

* **Technical Challenges:**
  * Multicollinearity between features  
  * Negative memory consumption instances  
  * Model generalization concerns

### Future Improvements

* **Data Enhancement:**
  * Extended time period analysis (monthly/yearly)  
  * Additional feature collection  
  * Improved data quality validation

* **Methodological Improvements:**
  * Advanced feature engineering  
  * Ensemble modeling approaches  
  * Deep learning implementation

* **Analysis Extension:**
  * Application-specific optimization studies  
  * Cross-system comparisons  
  * Long-term trend analysis

---

## Conclusion

The project successfully analyzed Cori's resource utilization patterns, developed accurate predictive models, and proposed concrete optimization strategies. The random forest model demonstrated superior predictive performance, while the correlation analysis revealed important relationships between different resource metrics. The identified patterns and strategies provide a foundation for improving system efficiency and resource allocation.

---

## Technical Notes

* All code implementations are available in R scripts  
* Visualization outputs are preserved in high-resolution formats  
* Statistical analysis results are documented with confidence intervals  
* Model parameters and hyperparameters are fully documented
