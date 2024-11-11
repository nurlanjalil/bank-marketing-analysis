# Bank Direct Marketing Campaign Analysis

This project analyzes a bank's direct marketing campaign dataset to understand factors affecting customer deposit behavior. The analysis includes data preprocessing, descriptive analysis, outlier handling, feature engineering, and binary classification modeling to predict deposit likelihood.

## General Descriptive Analysis

1. **Data Loading and Basic Information**:
   - Loaded data using `pandas`.
   - Dataset overview: `df.head()`, `df.shape`, and `df.columns`.
   - Renamed columns for better readability.

2. **Target Variable Distribution**:
   - Checked the number of unique values in each column.
   - Observed that the number of non-depositors is significantly higher.
   - Plotted target variable distribution to highlight the class imbalance.

3. **Monthly Deposits Trend**:
   - Reordered months for accurate chronological plotting.
   - Observed a partial increase in depositors during summer months.

4. **Depositor Analysis by Demographics**:
   - Analyzed depositor behavior by `job`, `age`, and `contact` type.
   - Middle-aged people and cellular contacts had higher deposit rates.

5. **Outlier Treatment**:
   - Detected and handled outliers in the `age` column using IQR.
   - Used `clip()` function for compressing outliers without removing data points.

6. **Missing Values**:
   - Verified no missing values were present in the dataset.

7. **Feature Engineering**:
   - Applied **Optimal Binning** to group `age` and `campaign` into bins.
   - Used **MinMaxScaler** and **StandardScaler** for normalization and standardization.

## Binary Classification Models

We experimented with various classification models, addressing class imbalance using **SMOTE** for oversampling. Below are the model evaluation metrics:

| Model                  | Accuracy | Precision | Recall   | F1 Score |
|------------------------|----------|-----------|----------|----------|
| Gradient Boosting      | 0.872    | 0.914     | 0.822    | 0.865    |
| Logistic Regression    | 0.765    | 0.799     | 0.708    | 0.751    |
| Naive Bayes            | 0.712    | 0.745     | 0.645    | 0.691    |
| Support Vector Machines| 0.765    | 0.805     | 0.701    | 0.749    |
| K-Nearest Neighbors    | 0.861    | 0.821     | 0.923    | 0.869    |
| **Random Forest**      | **0.940**| **0.940** | **0.939**| **0.940**|
| Balanced Random Forest | 0.939    | 0.939     | 0.940    | 0.940    |
| Decision Tree          | 0.900    | 0.892     | 0.911    | 0.902    |

### Best Performing Model
The **Random Forest** classifier performed best in terms of accuracy, precision, recall, and F1 score, making it the optimal model for predicting deposit likelihood.

## Conclusion
This analysis provides insights into customer behavior in a bank's direct marketing campaign and demonstrates effective techniques for handling class imbalance, feature engineering, and model selection.
