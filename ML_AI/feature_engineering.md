# Feature engineering

## Handling missing value

-   Handling missing value is a key step in cleaning data,
-   Missing values can significantly distort statistical summaries and degrade model performance. 
-   The approach depends on the nature, volume, and cause of missing data.

### Types of Missing Data

Handling methods should consider why data are missing:

-   **MCAR (Missing Completely at Random):** It is unrelated to any variable. These can often be safely removed or imputed.
-   **MAR (Missing at Random):** It depends on observed data.
-   **MNAR (Missing Not at Random):** It depends on unobserved factors. These require specialised approaches such as model-based imputations.

### Technique to handle missing value

#### 1. Deletion Methods

-   **Listwise deletion:** Removes any rows with missing data in any column, useful when missing data are rare.

    ```python
    df.dropna(inplace=True)
    ```

-   **Pairwise deletion:** Retains as much data as possible by removing missing values only for relevant variables.

#### 2. Simple Imputation

Replaces missing values with summary statistics of non-missing data:

-   **Mean Imputation:** For continuous variables.

    ```python
    df['Age'].fillna(df['Age'].mean())
    ```

-   **Median Imputation:** Useful when outliers exist.

-   **Mode Imputation:** For categorical data features.

#### 3. Advanced Imputation

-   **KNN Imputation:** Estimates missing values based on nearest neighbors in feature space using *sklearn.impute.KNNImputer*.
-   **Iterative Imputation:** Uses regression models to predict missing values iteratively (*sklearn.impute.IterativeImputer*).
-   **Multiple Imputation:** Creates several imputed datasets and averages results to reduce bias.

#### 4. Interpolation

Numerical methods estimate values between observed points, e.g. *linear* or *spline* interpolation.

```python
df['Value'].interpolate(method='linear', inplace=True)
```

This is suitable for time series or sequential numerical data.

#### 5. Encoding Missingness

Instead of filling missing data, missingness itself can be treated as a predictive feature by creating a binary flag column indicating the presence of missing values.

#### 6. Model-Based Approaches

Predict missing values using regression models or machine learning algorithms trained on features without missing entries. This approach is common for large datasets where imputations must be contextual.

## Handling Imbalance Dataset

-   When we have a imbalance dataset then out model will be biased towards the category with more imbalance value
-   We can use:
    -   Up sampling
    -   Down sampling

### Up sampling

-   Interpolate new data for the categories with the less frequency sample (SMOTE, ADASYN, SIMO)
-   This will add samples to the dataset to reduce biasness in the data

## Down sampling

-   Here we remove the data from the biased category 
-   The number of samples are reduced 
-   This is not recommended if the dataset us small or huge count of the majority and minority is observed



### SMOTE

-   SMOTE stands for **Synthetic Minority Over-sampling Technique**, and it generates synthetic samples for the minority class to balance the dataset.
-   Instead of duplicating minority samples, SMOTE creates **synthetic examples** by interpolating between existing ones. 
-   This helps reduce overfitting and improves generalization.

### ADASYN

-   ADASYN (Adaptive Synthetic Sampling) is another powerful technique for handling imbalanced datasets. 

-   Focuses on samples that are harder to learn (i.e., near decision boundaries), making the classifier more robust.

-   It generates **more synthetic samples** for these difficult cases and **fewer** for easier ones.

-   The total number of synthetic samples is based on a **desired imbalance ratio**, not necessarily full balance.


## Handling Outlier

-   To handle outliers effectively, you can detect them using statistical methods like Z-score or IQR, and then choose to remove, cap, or transform them based on your analysis goals.

### **🔍 Detection Techniques**

1.  **Z-score Method**
    -   Calculates how many standard deviations a data point is from the mean.
    -   Typically, values with a Z-score > 3 or < -3 are considered outliers.
    -   Best for normally distributed data.
2.  **Interquartile Range (IQR)**
    -   Based on the spread between the 25th (Q1) and 75th (Q3) percentiles.
    -   Outliers fall below Q1 - 1.5×IQR or above Q3 + 1.5×IQR.
    -   Robust against non-normal distributions.
3.  **Isolation Forest**
    -   An ensemble method that isolates anomalies by randomly selecting features and split values.
    -   Effective for high-dimensional datasets.
4.  **Local Outlier Factor (LOF)**
    -   Measures the local density deviation of a data point compared to its neighbors.
    -   Useful for detecting outliers in clusters.
5.  **Mahalanobis Distance**
    -   Measures distance from the mean considering correlations between variables.
    -   Suitable for multivariate outlier detection.

### 🛠️ **Handling Strategies**

-   **Remove Outliers**
    -   Safest when outliers are due to data entry errors or irrelevant anomalies.
    -   Risk: Loss of valuable information if outliers are meaningful.
-   **Cap or Winsorize**
    -   Replace extreme values with a threshold (e.g., 5th and 95th percentiles).
    -   Preserves data size while reducing impact.
-   **Transform Data**
    -   Apply log, square root, or Box-Cox transformations to reduce skewness.
    -   Helps normalize distributions and reduce outlier influence.
-   **Impute Values**
    -   Replace outliers with mean, median, or predicted values.
    -   Useful when data integrity must be preserved.
-   **Use Robust Models**
    -   Some algorithms (e.g., tree-based models) are less sensitive to outliers.
    -   Consider switching to models that handle noise better.

### ⚠️ **When to Keep Outliers**

Outliers may represent rare but important phenomena (e.g., fraud detection, medical anomalies). Always assess their context before removal.

| Method               | Best For                         | Assumptions          | Pros                                   | Cons                                   |
| -------------------- | -------------------------------- | -------------------- | -------------------------------------- | -------------------------------------- |
| **Z-Score**          | Normal distributions             | Data is Gaussian     | Simple, fast, interpretable            | Sensitive to mean/variance, not robust |
| **IQR**              | Skewed or non-normal data        | None                 | Robust to outliers, easy to compute    | Ignores multivariate structure         |
| **Isolation Forest** | High-dimensional, large datasets | None                 | Fast, works well with many features    | May misclassify rare but valid points  |
| **LOF**              | Clustered or local anomalies     | Density-based        | Captures local structure, unsupervised | Sensitive to `n_neighbors` parameter   |
| **Mahalanobis**      | Multivariate Gaussian data       | Linear relationships | Accounts for feature correlation       | Requires invertible covariance matrix  |



## Data Encoding

-   Data encoding transforms categorical variables into numerical formats so machine learning models can process them effectively. 

    ### Types of Categorical Data

    -   **Binary**: Two categories (e.g., Yes/No)
    -   **Ordinal**: Ordered categories (e.g., Low, Medium, High)
    -   **Nominal**: Unordered categories (e.g., Red, Blue, Green)

### Common Encoding Techniques

| Technique              | Best For         | Description                                                  | Pros                              | Cons                            |
| ---------------------- | ---------------- | ------------------------------------------------------------ | --------------------------------- | ------------------------------- |
| **One-Hot Encoding**   | Nominal          | Creates binary columns for each category.                    | Preserves category independence   | Increases dimensionality        |
| **Label Encoding**     | Ordinal          | Assigns each category a unique integer.                      | Simple, fast                      | Imposes order where none exists |
| **Ordinal Encoding**   | Ordinal          | Maps categories to ordered integers.                         | Retains order                     | Assumes equal spacing           |
| **Target Encoding**    | Nominal/Ordinal  | Replaces category with mean of target variable.              | Captures relationship with target | Risk of data leakage            |
| **Frequency Encoding** | Nominal          | Replaces category with its frequency count.                  | Simple, preserves distribution    | May lose semantic meaning       |
| **Binary Encoding**    | High-cardinality | Converts categories to binary digits and splits into columns. | Reduces dimensionality            | Less interpretable              |