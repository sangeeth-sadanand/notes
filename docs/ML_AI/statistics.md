# Statistics

**Statistics** is the branch of mathematics that deals with the **collection, organization, analysis, interpretation, and presentation of data**.  

## Introduction

### Role of Statistics in ML and Data Science

Statistics plays a vital role in ML and Data Science by enabling:

- **Data Summarization**: Condenses large datasets into interpretable summaries (mean, median, mode, variance, etc.).
- **Understanding Relationships**: Identifies patterns and correlations between variables.
- **Probability Modeling**: Helps model uncertainty and make predictions.
- **Hypothesis Testing**: Assesses assumptions and validates models.
- **Feature Selection and Engineering**: Guides which variables to include in models.
- **Model Evaluation**: Statistical metrics (MSE, RMSE, R²) are used to evaluate predictive performance.
- **Decision Making**: Facilitates informed decisions based on data-driven insights.

### Descriptive vs. Inferential Statistics

#### **Descriptive Statistics**

- **Purpose**: Summarizes and describes the main features of a dataset.
- **Techniques**:
  - **Central Tendency**: Mean, Median, Mode
  - **Dispersion**: Range, Variance, Standard Deviation, IQR
  - **Visualization**: Histograms, Boxplots, Bar Charts, Scatter Plots
- **Use Case**: Quick understanding of dataset characteristics.

#### **Inferential Statistics**

- **Purpose**: Makes predictions or inferences about a **population** based on a **sample**.
- **Techniques**:
  - Hypothesis Testing (t-test, chi-square test, ANOVA)
  - Confidence Intervals
  - Regression Analysis
  - Correlation Analysis
- **Use Case**: Generalizing findings beyond the observed data.

###  Population vs. Sample

| Term           | Definition                                                   | Example                                  |
| -------------- | ------------------------------------------------------------ | ---------------------------------------- |
| **Population** | The entire set of items or observations of interest          | All users of a social media platform     |
| **Sample**     | A subset of the population used to estimate population properties | 1,000 users randomly selected for survey |

**Key Points:**

- Samples are used because collecting data from the entire population is often impractical.
- Statistical inference allows conclusions about the population from the sample.
- **Bias** must be minimized to ensure sample represents population accurately.



### Variables and Types of Variables

 a **variable** is a **characteristic, attribute, or property** that can take on different values for different individuals or observations. Variables are fundamental because they represent the data we collect, analyze, and model.  

#### Types of Variables

Variables are broadly classified into **Quantitative (Numerical)** and **Qualitative (Categorical)** variables.  

##### 1. Quantitative (Numerical) Variables

- Represent measurable quantities.
- Can be **counted or measured**.
- Subtypes:
  1. **Discrete Variables**: Take **countable** values, usually integers.
     - Example: Number of students in a class, number of cars in a parking lot.
  2. **Continuous Variables**: Can take **any value** within a range.
     - Example: Height, Weight, Temperature, Age (measured precisely).

##### 2. Qualitative (Categorical) Variables

- Represent **categories or labels** rather than numeric values.
- Subtypes:
  1. **Nominal Variables**
     - Categories **without order**.
     - Example: Gender, Blood Type, Color.
  2. **Ordinal Variables**
     - Categories **with a meaningful order**, but intervals between categories are not uniform.
     - Example: Rating scales (Poor, Average, Good, Excellent), Education Level.

##### 3. Other Variable Types

- **Binary / Dichotomous Variables**
  - Only **two categories** (0 or 1, Yes or No).
  - Example: Has disease (Yes/No), Pass/Fail.
- **Interval Variables**
  - Numeric variables with **equal intervals** but **no true zero**.
  - Example: Temperature in Celsius or Fahrenheit.
- **Ratio Variables**
  - Numeric variables with **equal intervals** and a **true zero**.
  - Example: Height, Weight, Age, Income.

---

#### Summary

| Variable Type                 | Definition                             | Examples                    |
| ----------------------------- | -------------------------------------- | --------------------------- |
| **Quantitative / Numerical**  | Measurable quantities                  | Height, Weight, Age         |
| - Discrete                    | Countable, finite                      | Number of students, Cars    |
| - Continuous                  | Any value in a range                   | Temperature, Weight         |
| **Qualitative / Categorical** | Categories or labels                   | Gender, Blood Type          |
| - Nominal                     | No order                               | Color, City, Marital Status |
| - Ordinal                     | Ordered categories                     | Ratings, Education Level    |
| **Binary / Dichotomous**      | Two categories only                    | Yes/No, True/False          |
| **Interval**                  | Numeric, equal intervals, no true zero | Temperature (°C, °F), IQ    |
| **Ratio**                     | Numeric, equal intervals, true zero    | Age, Salary, Weight         |





### Scale of Measurement

The **scale of measurement** defines how data values are **quantified, categorized, and interpreted**. It determines the types of statistical analyses that are appropriate for the data.

#### Types of Scales

1. **Nominal Scale**
   - **Definition**: Data are categorized into distinct groups with **no natural order**.
   - **Operations**: Counting, mode
   - **Examples**: Gender, Blood Type, Eye Color

2. **Ordinal Scale**
   - **Definition**: Data are categorized with a **meaningful order**, but the intervals between categories are **not necessarily equal**.
   - **Operations**: Ranking, median, percentiles
   - **Examples**: Customer satisfaction (Poor, Fair, Good, Excellent), Education Level (High School, Bachelor’s, Master’s)

3. **Interval Scale**
   - **Definition**: Numeric data with **equal intervals** between values, but **no true zero point**.
   - **Operations**: Addition, subtraction, mean, standard deviation
   - **Examples**: Temperature in Celsius/Fahrenheit, IQ scores
   - **Note**: Ratios are **not meaningful** (e.g., 20°C is not “twice as hot” as 10°C).

4. **Ratio Scale**
   - **Definition**: Numeric data with **equal intervals** and a **true zero point**.
   - **Operations**: All arithmetic operations, including ratios
   - **Examples**: Height, Weight, Age, Income
   - **Note**: Zero means absence of the property, so statements like “twice as much” are meaningful.

### Sampling Techniques

#### Probability Sampling

In probability sampling, **each member of the population has a known, non-zero chance of being selected**. This allows for **statistical inference**.

##### **Simple Random Sampling (SRS)**

- Every individual has an **equal chance** of being selected.
- Methods: Random number generators, lottery method.
- Example: Selecting 100 students randomly from a university.

##### **Systematic Sampling**

- Select every **k-th member** from a population list after a random start.
- Example: Choosing every 10th customer entering a store.

##### **Stratified Sampling**

- Population divided into **homogeneous subgroups (strata)**, and a random sample is taken from each stratum.
- Ensures representation from all subgroups.
- Example: Sampling students by department to represent each department proportionally.

##### **Cluster Sampling**

- Population divided into **clusters** (often naturally occurring groups), and entire clusters are randomly selected.
- More practical for large, spread-out populations.
- Example: Selecting certain schools from a city and surveying all students in those schools.

##### **Multistage Sampling**

- Combines several sampling methods in stages.
- Example: Randomly selecting districts → then schools → then students within schools.

#### Non-Probability Sampling

In non-probability sampling, **not all members have a known or equal chance of being selected**. Easier to implement but may introduce bias.

##### **Convenience Sampling**

- Selects members **easily accessible**.
- Example: Surveying people passing by a mall.
- Limitation: May not be representative.

##### **Judgmental / Purposive Sampling**

- Members are chosen based on **expert judgment**.
- Example: Selecting key industry experts for an interview.

##### **Quota Sampling**

- Ensures certain **characteristics are represented**, but selection is non-random.
- Example: Ensuring 50% male and 50% female respondents in a survey.

##### **Snowball Sampling**

- Existing participants recruit **future participants** from their acquaintances.
- Useful for **hard-to-reach populations**.
- Example: Studying a rare disease or underground community.

####  Summary Table

| Sampling Type       | Method                 | Key Feature                 | Example                     |
| ------------------- | ---------------------- | --------------------------- | --------------------------- |
| **Probability**     | Simple Random          | Equal chance                | Random students             |
|                     | Systematic             | Every k-th selected         | Every 10th customer         |
|                     | Stratified             | Proportional representation | Students by department      |
|                     | Cluster                | Randomly selected clusters  | Schools in a city           |
|                     | Multistage             | Multiple stages             | District → School → Student |
| **Non-Probability** | Convenience            | Easily accessible           | Mall visitors               |
|                     | Judgmental / Purposive | Expert-selected             | Industry experts            |
|                     | Quota                  | Fixed quotas                | Gender-balanced survey      |
|                     | Snowball               | Participant referrals       | Rare disease study          |













---

---

---



### 2. Data Summarization and Descriptive Statistics

-   Measures of central tendency (mean, median, mode)
-   Measures of dispersion (range, variance, standard deviation, IQR)
-   Skewness and kurtosis
-   Five-number summary
-   Summary statistics in datasets

### 3. Probability Fundamentals

-   Basic probability concepts
-   Sample space and events
-   Conditional probability
-   Bayes’ theorem
-   Independence and mutual exclusivity

### 4. Random Variables and Probability Distributions

-   Discrete vs. continuous random variables
-   Probability mass and density functions
-   Expectation and variance
-   Common discrete distributions (Bernoulli, Binomial, Poisson)
-   Common continuous distributions (Uniform, Normal, Exponential)

### 5. Normal Distribution and Central Limit Theorem

-   Properties of the normal distribution
-   Standard normal distribution and z-scores
-   Central Limit Theorem
-   Practical implications for ML

### 6. Data Visualization for Statistical Analysis

-   Histograms and density plots
-   Box plots and violin plots
-   Scatter plots and pair plots
-   Correlation heatmaps
-   Visualization pitfalls

### 7. Correlation and Covariance

-   Covariance and interpretation
-   Pearson correlation coefficient
-   Spearman rank correlation
-   Multicollinearity
-   Correlation vs. causation

### 8. Statistical Inference

-   Sampling methods
-   Point estimation
-   Confidence intervals
-   Bias and variance trade-off
-   Estimation errors

### 9. Hypothesis Testing

-   Null and alternative hypotheses
-   Type I and Type II errors
-   p-values and significance levels
-   Common tests (z-test, t-test, chi-square test)
-   A/B testing fundamentals

### 10. Statistical Assumptions in Machine Learning

-   Linearity
-   Normality
-   Homoscedasticity
-   Independence of observations
-   Identifying assumption violations

### 11. Outliers and Data Quality

-   Detecting outliers (IQR, z-score)
-   Impact of outliers on ML models
-   Handling missing data
-   Data normalization and standardization

### 12. Basic Statistical Concepts in ML Algorithms

-   Loss functions and statistical meaning
-   Maximum likelihood estimation
-   Bias-variance decomposition
-   Overfitting and underfitting from a statistical view

### 13. Practical Statistics with Python (Optional)

-   NumPy and Pandas for statistics
-   SciPy for probability and hypothesis testing
-   Visualization with Matplotlib and Seaborn
-   Real-world ML dataset examples