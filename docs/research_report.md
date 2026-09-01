# Research Report

## 1. Introduction

This project presents an exploratory analysis of the **Iris Flower Dataset**. The objective is to understand the dataset structure, assess its quality, explore feature distributions, compare the three iris species, and identify relationships between numerical features.

The analysis was performed using **Python, Pandas, Matplotlib, and Seaborn**.

## 2. Dataset

The dataset contains **150 observations and 6 columns**:

* `Id`
* `SepalLengthCm`
* `SepalWidthCm`
* `PetalLengthCm`
* `PetalWidthCm`
* `Species`

The dataset contains three species: **Iris-setosa, Iris-versicolor, and Iris-virginica**, with **50 observations for each species**.

## 3. Data Quality

The dataset contains **no missing values** and **no duplicate rows**. Therefore, no missing-value treatment or duplicate removal was required.

The `Id` column was treated only as an identifier, while the four flower measurements were used as numerical features.

## 4. Exploratory Analysis

Descriptive statistics and visualizations were used to examine the four numerical features.

The analysis showed that **petal length and petal width have greater variation and stronger differences between species** than the sepal measurements.

Boxplots showed that Iris-setosa has considerably smaller petal measurements, while Iris-virginica generally has the largest petal measurements. Iris-versicolor lies between the two and has some overlap with Iris-virginica.

The scatter plot of **petal length versus petal width** showed three relatively distinct groups, indicating that these two features are useful for distinguishing the species.

Correlation analysis also showed a **strong positive relationship between petal length and petal width**.

## 5. Key Findings

* The dataset is clean, with no missing or duplicate records.
* The three species are equally represented.
* Petal length and petal width provide strong separation between species.
* Iris-setosa is clearly distinguishable from the other species using petal measurements.
* Iris-versicolor and Iris-virginica show some overlap.
* Petal length and petal width have a strong positive relationship.

## 6. Conclusion

The exploratory analysis shows that the Iris dataset is clean, balanced, and suitable for further Data Science analysis. The visualizations and statistical analysis indicate that **petal length and petal width are the most informative features for distinguishing the three iris species**.

The detailed analysis, visualizations, and individual findings are documented in `dataset_exploration.md`.

