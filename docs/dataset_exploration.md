# Dataset Exploration Report

## 1. Introduction

This report presents the exploration and analysis of the Iris Flower Dataset. The purpose of the analysis is to understand the structure and quality of the dataset, examine the distributions of the flower measurements, identify differences between species, and study relationships between the numerical features.

The analysis was performed using Python and pandas for data inspection and matplotlib/seaborn for visualization.

---

## 2. Dataset Overview

The dataset contains measurements of three species of iris flowers:

* Iris-setosa
* Iris-versicolor
* Iris-virginica

Each observation contains measurements of the flower's sepal and petal.

The dataset contains **150 observations and 6 columns**.
.
.
| Column          | Description                            | Data Type   |
| --------------- | -------------------------------------- | ----------- |
| `Id`            | Unique identifier for each observation | Integer     |
| `SepalLengthCm` | Length of the sepal in centimetres     | Float       |
| `SepalWidthCm`  | Width of the sepal in centimetres      | Float       |
| `PetalLengthCm` | Length of the petal in centimetres     | Float       |
| `PetalWidthCm`  | Width of the petal in centimetres      | Float       |
| `Species`       | Species of the iris flower             | Categorical |

The four measurement columns are numerical, while `Species` is a categorical variable. The `Id` column is only an identifier and is not used as a meaningful measurement feature.

---

## 3. Data Quality Analysis

### 3.1 Missing Values

Missing values were checked for every column.

| Column          | Missing Values |
| --------------- | -------------: |
| `Id`            |              0 |
| `SepalLengthCm` |              0 |
| `SepalWidthCm`  |              0 |
| `PetalLengthCm` |              0 |
| `PetalWidthCm`  |              0 |
| `Species`       |              0 |

There are **no missing values** in any column. Therefore, no missing-value treatment or imputation was required.

### 3.2 Duplicate Records

The dataset was checked for duplicate rows.

**Number of duplicate rows: 0**

This means every row in the dataset is unique based on all available columns.

---

## 4. Species Distribution

The dataset contains three species, with 50 observations for each species.

| Species         | Count |
| --------------- | ----: |
| Iris-setosa     |    50 |
| Iris-versicolor |    50 |
| Iris-virginica  |    50 |

The dataset is therefore **balanced with respect to the target species**. Each species represents one-third of the observations.

This is useful for analysis because no species is heavily overrepresented compared with the others.

---

## 5. Descriptive Statistics

The main numerical statistics are:

| Feature         |  Mean | Minimum | Maximum | Standard Deviation |
| --------------- | ----: | ------: | ------: | -----------------: |
| `SepalLengthCm` | 5.843 |     4.3 |     7.9 |              0.828 |
| `SepalWidthCm`  | 3.054 |     2.0 |     4.4 |              0.434 |
| `PetalLengthCm` | 3.759 |     1.0 |     6.9 |              1.764 |
| `PetalWidthCm`  | 1.199 |     0.1 |     2.5 |              0.763 |

### Interpretation

The petal measurements have considerably larger variation than the sepal measurements.

For example, petal length ranges from **1.0 cm to 6.9 cm**, while sepal length ranges from **4.3 cm to 7.9 cm**.

The relatively large standard deviation of petal length also indicates that petal length varies considerably across the different flower species.

---

# 6. Exploratory Data Analysis

## 6.1 Distribution of Sepal Length

The histogram of `SepalLengthCm` shows that sepal length values are mainly concentrated around the middle of the observed range.

Most observations have sepal lengths between approximately **5 cm and 7 cm**. The distribution is not perfectly uniform, indicating that some ranges of sepal length occur more frequently than others.

This feature provides useful information about the physical size of the flowers, although the species are not separated as clearly using sepal length alone.

---

## 6.2 Distribution of Sepal Width

The `SepalWidthCm` histogram shows that most observations have sepal widths around **2.5 cm to 3.5 cm**.

Compared with petal measurements, sepal width has a relatively narrow range and lower standard deviation.

This indicates that sepal width varies less across the dataset than petal length.

---

## 6.3 Distribution of Petal Length

The `PetalLengthCm` histogram shows a much wider distribution.

The values range from **1.0 cm to 6.9 cm**, and the distribution contains distinct groups of observations.

This separation occurs because the three iris species have substantially different petal lengths.

Therefore, petal length appears to be one of the more useful features for distinguishing the species.

---

## 6.4 Distribution of Petal Width

The `PetalWidthCm` histogram shows a similar pattern to petal length.

Values range from **0.1 cm to 2.5 cm**, with groups of observations appearing at different parts of the range.

The clear differences in petal width between species suggest that this feature is also useful for identifying the species.

---

# 7. Boxplot Analysis

Boxplots were used to compare each numerical measurement across the three iris species.

## 7.1 Sepal Length by Species

The boxplot shows that the three species have different distributions of sepal length, although there is noticeable overlap.

Iris-setosa generally has shorter sepals than Iris-versicolor and Iris-virginica.

Iris-virginica generally has the largest sepal lengths.

However, because the distributions overlap, sepal length alone cannot perfectly distinguish all three species.

---

## 7.2 Sepal Width by Species

The boxplot for sepal width shows greater overlap between the species than the petal measurements.

Iris-setosa generally has a larger sepal width compared with the other species.

There is still considerable variation within the species, meaning that sepal width by itself is not a strong separator between all three groups.

---

## 7.3 Petal Length by Species

The petal-length boxplot shows a much clearer difference between species.

Iris-setosa has very small petal lengths compared with Iris-versicolor and Iris-virginica.

Iris-versicolor generally has intermediate petal lengths, while Iris-virginica has the largest petal lengths.

The distributions are therefore much more separated than those observed for the sepal measurements.

This makes petal length a particularly useful feature for distinguishing the species.

---

## 7.4 Petal Width by Species

Petal width shows a similar pattern to petal length.

Iris-setosa has very small petal widths, Iris-versicolor has intermediate values, and Iris-virginica generally has the largest values.

The strong separation between the species indicates that petal width is also a useful feature for species identification.

---

# 8. Petal Length vs Petal Width

A scatter plot was created using `PetalLengthCm` on the x-axis and `PetalWidthCm` on the y-axis.

The plot shows three relatively distinct groups corresponding to the three species.

**Iris-setosa** forms a clearly separated group with short and narrow petals.

**Iris-versicolor** occupies an intermediate region.

**Iris-virginica** generally has both longer and wider petals.

There is some overlap between Iris-versicolor and Iris-virginica, but the separation is still much clearer than for many of the sepal measurements.

### Finding

The scatter plot provides strong visual evidence that **petal length and petal width are useful features for distinguishing iris species**.

---

# 9. Correlation Analysis

Correlation was calculated between the four numerical measurement features.

Correlation measures the strength and direction of a linear relationship between two numerical variables.

A positive correlation means that as one feature increases, the other tends to increase as well.

The analysis shows that **petal length and petal width have a strong positive relationship**.

This means flowers with longer petals generally also tend to have wider petals.

The petal measurements also show strong relationships with the sepal measurements, while the relationship between sepal length and sepal width is comparatively weaker.

### Important observation

The strong relationship between petal length and petal width is consistent with the scatter plot, where the observations follow a clear upward pattern.

---

# 10. Overall Findings

The main findings from the exploratory analysis are:

### Finding 1 — The dataset is clean

There are no missing values and no duplicate rows. This means the dataset can be analyzed without performing basic data-cleaning operations such as missing-value imputation or duplicate removal.

### Finding 2 — The dataset is balanced

All three species contain exactly 50 observations. No species dominates the dataset.

### Finding 3 — Petal measurements are highly informative

Petal length and petal width show much clearer differences between species than the sepal measurements.

### Finding 4 — Iris-setosa is clearly different

Iris-setosa generally has much smaller petals than the other two species, making it relatively easy to distinguish from them using petal measurements.

### Finding 5 — Iris-versicolor and Iris-virginica are more similar

These two species show more overlap than Iris-setosa and the other species. However, their petal measurements still show noticeable differences.

### Finding 6 — Petal length and width are strongly related

Flowers with longer petals generally tend to have wider petals. This relationship is visible in the scatter plot and supported by the correlation analysis.

---

# 11. Key Insights from Visualizations

The visualizations provide several important insights:

1. **Histograms** show the distributions and ranges of the four numerical features.
2. **Boxplots** show that petal measurements differ considerably between species.
3. **The petal-length vs petal-width scatter plot** shows clear grouping of the three species.
4. **The correlation matrix** shows strong relationships between several numerical features, particularly between petal length and petal width.
5. The visual analysis suggests that **petal measurements are more effective than sepal measurements for separating the three species**.

---

# 12. Conclusion

The exploratory analysis shows that the Iris dataset is small, clean, balanced, and suitable for Data Science analysis.

The dataset contains 150 observations belonging equally to three species. No missing values or duplicate rows were found.

The visualizations and statistical analysis show that the most noticeable differences between species occur in **petal length and petal width**. Iris-setosa is particularly well separated from the other species, while Iris-versicolor and Iris-virginica have some overlap.

Overall, the analysis demonstrates how basic data inspection, descriptive statistics, and visualization can be used to discover patterns and relationships in a dataset before applying more advanced Data Science techniques.

