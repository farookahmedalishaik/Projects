# Optimizing Resource Utilization on the Cori Supercomputer

### Overview

This project focuses on optimizing resource utilization for the Cori supercomputer at the National Energy Research Scientific Computing Center (NERSC). By leveraging advanced computational methods and machine learning models, the project aims to uncover patterns in resource usage, predict future power consumption, and develop strategies to improve efficiency.

### Research Questions

1.**Descriptive Analysis:** How does the computational workload vary throughout the week?

2.**Predictive Modeling:** What is the optimal model for forecasting power usage?

3.**Correlation Analysis:** What are the relationships between power consumption, memory usage, and other variables?

4.**Strategy Development:** How can resource utilization be optimized for different types of applications?

5.**Identification of Improvement Areas:** What are the high-resource utilization periods, and how can they be addressed?

### Dataset

The dataset contains **4,401 observations** and **14 features**, including:

* **Categorical Variables:** exename, appname

* **Datetime Variables:** start, end

* **Numerical Variables:** jobid, numnodes, numcpus, numtasks, executiontime, power, memory, taskspercpu, taskspernode, user

Data source: Jobs executed on the Cori supercomputer during one week in 2020.

### Technologies Used

* **Programming Language:** R

* **Libraries:**

  * Data manipulation: tidyverse, lubridate

  * Data visualization: ggplot2, plotly, corrplot

  * Modeling: caret, randomForest

  * Metrics evaluation: Metrics, broom

### Methods

**Data Preparation**

  *Handled missing values and outliers.

  *Converted data types and metrics for consistency.

  *Performed exploratory data analysis (EDA) to visualize trends.

**Analysis Techniques**

1.**Descriptive Statistics:** Visualized execution time trends using bar charts and heatmaps.

2.**Predictive Modeling:**

  * **Linear Regression:** Basic predictive modeling.

  * **Polynomial Regression:** Improved non-linear relationships.

  * **Random Forest Regression:** Captured complex interactions with the best accuracy.

3.**Correlation Analysis:** Identified relationships using heatmaps and correlation matrices.

4.**Strategy Development:** Proposed optimization methods based on application-level insights.

### Evaluation Metrics

  *Cross-Validation (CV)

  *Root Mean Squared Error (RMSE)

  *Mean Squared Error (MSE)

  *Mean Absolute Error (MAE)

### Results

**Key Findings**

1.**Workload Patterns:**

  *Weekdays show higher computational load, peaking during business hours (6 AM - 7 PM).

  *Weekends exhibit reduced execution times.

2.**Optimal Predictive Model:** Random Forest achieved the lowest error metrics:

  *RMSE: 11.86

  *MSE: 140.66

  *MAE: 6.67

3.**Correlation Insights:**

  *Strong correlation between computational load and power consumption.

  *Moderate correlation between power and memory usage.

  *Weak correlation between memory and computational load.

4.**High Utilization Periods:**

  *Significant peaks in CPU and memory utilization on December 1st, 3rd, 5th, and 6th.

### Strategies for Improvement

  * **Application Optimization:** Enhance efficiency of resource-intensive applications (e.g., chroma, gene, qlua).

  * **Resource Scheduling:** Distribute workloads to avoid contention during peak hours.

  * **Load Balancing:** Dynamically allocate resources across nodes to handle spikes efficiently.

  * **Capacity Planning:** Use insights from patterns to plan hardware upgrades and allocation policies.

### Limitations and Future Work

**Limitations**

  *Data limited to a single week, reducing generalizability.

  *Instances of negative memory consumption suggest potential data errors.

  *Multicollinearity between features posed challenges.

**Future Improvements**

  *Expand analysis with larger datasets (monthly/yearly).

  *Address multicollinearity using advanced techniques.

  *Collaborate with domain experts to resolve data inconsistencies.

### Conclusion

This project successfully analyzed resource utilization on the Cori supercomputer, developed robust predictive models, and proposed actionable strategies for optimization. The methodologies and insights gained have broader applicability to other high-performance computing environments.
