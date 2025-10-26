# .Feature engineering

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

    