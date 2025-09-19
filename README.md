# python_week_seven_assignment

## Data Analysis and Visualization: Cleveland Heart Disease & Iris Datasets

### Overview

This project involves exploratory data analysis and visualization of two popular datasets:
- **Cleveland Heart Disease Dataset** — used for analyzing heart disease indicators and their relationship with patient attributes.
- **Iris Dataset** — a classic dataset for classification and clustering tasks, used here for data handling practice.

The goal is to clean, explore, and visualize key relationships within these datasets, focusing on meaningful insights related to health and classification.

---

### Datasets

#### Cleveland Heart Disease Dataset
- Contains medical attributes such as age, sex, cholesterol levels, maximum heart rate, ST depression (oldpeak), and disease status.
- The dataset is used to identify patterns and correlations associated with heart disease.
- Data includes both numerical and categorical features.

#### Iris Dataset
- Classic dataset with measurements of iris flowers: sepal length, sepal width, petal length, petal width, and species.
- Used to demonstrate dataset loading, exploration, and basic data cleaning.

---

Sure! Here's a detailed and well-structured **README.md** template you can use for your project involving the Cleveland Heart Disease and Iris datasets, including data loading, exploration, cleaning, and visualization:

---

````markdown
# Data Analysis and Visualization: Cleveland Heart Disease & Iris Datasets

## Overview

This project involves exploratory data analysis and visualization of two popular datasets:
- **Cleveland Heart Disease Dataset** — used for analyzing heart disease indicators and their relationship with patient attributes.
- **Iris Dataset** — a classic dataset for classification and clustering tasks, used here for data handling practice.

The goal is to clean, explore, and visualize key relationships within these datasets, focusing on meaningful insights related to health and classification.

---

## Datasets

### Cleveland Heart Disease Dataset
- Contains medical attributes such as age, sex, cholesterol levels, maximum heart rate, ST depression (oldpeak), and disease status.
- The dataset is used to identify patterns and correlations associated with heart disease.
- Data includes both numerical and categorical features.

### Iris Dataset
- Classic dataset with measurements of iris flowers: sepal length, sepal width, petal length, petal width, and species.
- Used to demonstrate dataset loading, exploration, and basic data cleaning.

---

## Project Steps

### 1. Data Loading

- Loaded both datasets from CSV files using `pandas`.
- Displayed the first few rows using `.head()` to inspect data structure.

```python
import pandas as pd

df_heart = pd.read_csv('cleveland_heart.csv')
df_iris = pd.read_csv('iris.csv')

print(df_heart.head())
print(df_iris.head())
````

---

### 2. Data Exploration

* Checked data types and presence of missing values using `.dtypes`, `.info()`, and `.isnull().sum()`.
* For Cleveland dataset, mapped categorical variables (e.g., `sex`: 0 = Female, 1 = Male) to meaningful labels.
* Inspected distributions and summary statistics.

```python
print(df_heart.info())
print(df_heart.isnull().sum())

df_heart['gender'] = df_heart['sex'].map({0: 'Female', 1: 'Male'})
```

---

### 3. Data Cleaning

* Handled missing values by either dropping or filling them, depending on the context.
* For the Iris dataset, ensured no missing data remained.
* Created combined or new categorical columns when necessary for visualization clarity.

---

### 4. Data Visualization

Used `matplotlib` and `seaborn` for insightful visualizations:

#### Cleveland Heart Disease Dataset Visualizations:

* **Line Chart:** Plotted Age vs. Cholesterol by Sex, with confidence intervals to understand cholesterol trends across ages by gender.
* **Bar Chart:** Compared ST Depression (oldpeak) values by Gender and Disease Status, showing differences in heart stress between groups.
* **Histogram:** Displayed distribution of Maximum Heart Rate by Sex, highlighting differences in cardiovascular performance.

```python
import seaborn as sns
import matplotlib.pyplot as plt

# Example: Histogram of Max Heart Rate by Gender
sns.histplot(data=df_heart, x="thalach", bins=20, hue="gender", kde=True)
plt.title("Distribution of Max. Heart Rate by Sex")
plt.xlabel("Maximum Heart Rate (thalach/bpm)")
plt.ylabel("Frequency")
plt.tight_layout()
plt.show()
```

#### Iris Dataset Visualizations:

* Though not detailed here, typical visualizations include scatterplots colored by species to explore feature separability.

---

### Key Insights

* **Heart Disease Data:**

  * Cholesterol levels vary with age but are generally similar across genders.
  * ST Depression (oldpeak) is notably higher in patients with disease, irrespective of gender.
  * Males tend to achieve higher maximum heart rates than females.
* **Iris Dataset:**

  * Simple dataset used primarily for demonstrating data handling and cleaning workflows.

---

### Tools and Libraries

* Python 3.x
* pandas & numpy — for data manipulation
* matplotlib & seaborn — for visualization
* os — for file loading, and
* from sklearn.datasets import load_iris

---

### How to Run

1. Install dependencies:

   ```bash
   pip install pandas matplotlib seaborn numpy os
   ```

2. Clone the repository.

3. Run the Jupyter notebooks that perform the loading, cleaning, and visualization steps.

---

### Future Work

* Perform statistical tests to confirm significance of observed differences.
* Build predictive models for heart disease classification.
* Explore feature engineering and dimensionality reduction techniques on Iris dataset.

---

### References

* [Cleveland Heart Disease Dataset (UCI Repository)](https://archive.ics.uci.edu/ml/datasets/heart+Disease)
* [Iris Dataset](https://archive.ics.uci.edu/ml/datasets/iris)

---

*Prepared by \[C. Divinegift Akuwudike]*

---

