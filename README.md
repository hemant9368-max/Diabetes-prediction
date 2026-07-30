# Diabetes Dataset Preprocessing using Pandas

## Project Overview

This project performs data preprocessing on the Diabetes dataset using Python and Pandas. The objective is to clean the dataset by handling missing values and preparing it for machine learning.

## Tools and Libraries

* Python
* Pandas
* NumPy

## Dataset

The dataset used is `diabetes.csv`, which contains 768 records and 9 columns.

### Features

* Pregnancies
* Glucose
* BloodPressure
* SkinThickness
* Insulin
* BMI
* DiabetesPedigreeFunction
* Age
* Diabetes (Target Variable)

## Steps Performed

### 1. Import Libraries

Imported the required libraries:

* pandas
* numpy

### 2. Load Dataset

Loaded the dataset using:

```python
df = pd.read_csv("diabetes.csv")
```

### 3. Data Exploration

Performed basic analysis using:

* `df.head()`
* `df.tail()`
* `df.shape`
* `df.columns`
* `df.info()`
* `df.describe()`

### 4. Check Missing Values

Checked for missing values using:

```python
df.isnull().sum()
```

Initially, no null values were found.

### 5. Identify Invalid Zero Values

The following columns contained zero values that represent missing data:

* Pregnancies
* Glucose
* BloodPressure
* SkinThickness
* Insulin
* BMI

### 6. Replace Zero Values

Replaced zero values with `NaN`:

```python
df[cols] = df[cols].replace(0, np.nan)
```

### 7. Handle Missing Values

Filled missing values with the median of each column:

```python
for col in cols:
    df[col] = df[col].fillna(df[col].median())
```

### 8. Verify Dataset

Confirmed that all missing values were removed:

```python
df.isnull().sum()
```

## Result

* Dataset size: **768 rows × 9 columns**
* All missing values handled successfully.
* Data is cleaned and ready for machine learning model training.

## Conclusion

The preprocessing pipeline successfully:

* Loaded the dataset.
* Explored the data.
* Identified invalid zero values.
* Replaced them with `NaN`.
* Filled missing values using the median.
* Produced a clean dataset suitable for classification models such as Logistic Regression, Decision Tree, Random Forest, KNN, or SVM.
