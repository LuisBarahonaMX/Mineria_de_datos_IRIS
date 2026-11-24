# Iris Data Mining | K-Means Clustering and Exploratory Data Analysis

### Unsupervised Machine Learning, Data Preprocessing, and Cluster Evaluation with Python

**Project Type:** Academic Data Mining Project  
**Field:** Data Science | Machine Learning | Unsupervised Learning  
**Author:** Data Engineer Luis Barahona  
**Environment:** Google Colab | Jupyter Notebook

---

## 1. Project Overview

This project explores data mining and unsupervised machine learning techniques using the Iris flower dataset.

The main objective is to analyze botanical measurements, identify patterns among flower species, and apply the K-Means clustering algorithm to discover groups based on numerical characteristics.

The notebook covers data exploration, preprocessing, feature standardization, cluster selection, model implementation, and interpretation of results.

Unlike supervised classification, K-Means identifies groups without using the species labels during training.

## 2. Dataset Description

The dataset contains 150 observations distributed across three Iris flower species:

- Iris-setosa
- Iris-versicolor
- Iris-virginica

### Dataset Structure

| Feature | Description |
|:---|:---|
| Id | Unique observation identifier |
| SepalLengthCm | Sepal length in centimeters |
| SepalWidthCm | Sepal width in centimeters |
| PetalLengthCm | Petal length in centimeters |
| PetalWidthCm | Petal width in centimeters |
| Species | Flower species label |

**Dataset characteristics:**

- 150 rows
- 6 original columns
- 4 numerical measurement features
- 3 flower species
- No missing values
- No duplicate rows

The `Id` column is removed before clustering because it does not represent a meaningful botanical characteristic.

## 3. Project Objectives

- Explore and understand the Iris dataset.
- Identify missing values and duplicate records.
- Perform exploratory data analysis (EDA).
- Visualize relationships between botanical measurements.
- Standardize numerical features using StandardScaler.
- Apply K-Means clustering.
- Evaluate different numbers of clusters.
- Use the Elbow Method and Silhouette Score.
- Compare identified clusters with actual species labels.
- Interpret the characteristics of each cluster.

## 4. Methodology

### Step 1 — Data Loading

The Iris dataset is uploaded to Google Colab as `Iris.csv`.

Pandas is used to load the dataset and inspect its structure, data types, descriptive statistics, and completeness.

### Step 2 — Data Cleaning

A copy of the original dataset is created.

The `Id` column is removed, and four numerical features are selected for clustering.

### Step 3 — Feature Standardization

StandardScaler is applied to standardize the numerical variables.

This step helps prevent features with larger numerical scales from disproportionately influencing Euclidean distance calculations in K-Means.

### Step 4 — Exploratory Data Analysis

The notebook includes:

- Species distribution visualization.
- Sepal length versus sepal width scatter plots.
- Petal length versus petal width scatter plots.
- Correlation heatmap of numerical features.

These visualizations help identify relationships and potential natural groupings.

### Step 5 — Elbow Method

K-Means models are evaluated using cluster counts from 1 to 10.

For each configuration, the within-cluster inertia is calculated and plotted.

The Elbow Method provides a visual approach to exploring appropriate cluster counts.

### Step 6 — Silhouette Analysis

Silhouette Scores are calculated for cluster counts from 2 to 10.

This metric evaluates how closely observations are grouped within their assigned clusters relative to neighboring clusters.

### Step 7 — K-Means Clustering

A final K-Means model is configured with:

- Number of clusters: 3
- Random state: 42
- Number of initializations: 10

The algorithm assigns a cluster label to each observation using the four standardized numerical features.

### Step 8 — Cluster Interpretation

The resulting clusters are analyzed using:

- Scatter plots.
- Cluster frequency distributions.
- Cluster-to-species contingency tables.
- Average botanical measurements by cluster.

Actual species labels are used for interpretation after clustering, not as training targets.

---

## 5. Experimental Results

### Silhouette Score Comparison

| Clusters (k) | Silhouette Score |
|:---:|---:|
| 2 | 0.5802 |
| 3 | 0.4590 |
| 4 | 0.3853 |
| 5 | 0.3473 |
| 6 | 0.3407 |
| 7 | 0.3288 |
| 8 | 0.3404 |
| 9 | 0.3427 |
| 10 | 0.3404 |

**Observation:** The highest Silhouette Score was obtained with k = 2.

However, the notebook selects k = 3 for the final experiment to explore how the clustering structure relates to the three known Iris species.

This distinction is important: k = 3 is an experimental choice, not the optimal value according to the Silhouette Score.

### Cluster Distribution by Species

| Cluster | Iris-setosa | Iris-versicolor | Iris-virginica |
|:---:|---:|---:|---:|
| 0 | 0 | 39 | 14 |
| 1 | 50 | 0 | 0 |
| 2 | 0 | 11 | 36 |

### Key Findings

- Iris-setosa forms a clearly separated cluster.
- Iris-versicolor and Iris-virginica show overlapping characteristics.
- Petal length and petal width provide useful visual separation between species.
- Standardized numerical features allow K-Means to identify meaningful patterns without using species labels.
- The clustering results demonstrate both the capabilities and limitations of unsupervised learning.

---

## 6. Technologies Used

| Technology | Purpose |
|:---|:---|
| Python | Programming language |
| Pandas | Data loading and manipulation |
| NumPy | Numerical operations |
| Matplotlib | Data visualization |
| Seaborn | Statistical visualization |
| Scikit-learn | Scaling, K-Means, and Silhouette Score |
| Google Colab | Cloud-based notebook environment |
| Jupyter Notebook | Interactive analysis and documentation |

## 7. How to Run

### Option 1 — Google Colab

Open the original notebook:

[Open Iris Data Mining Notebook in Google Colab](https://colab.research.google.com/drive/1rYK1C3h90eAYOohLTHHnUV_bI5T1igxC)

1. Open the notebook in Google Colab.
2. Upload the `Iris.csv` dataset when prompted.
3. Run the cells sequentially.
4. Review the exploratory visualizations.
5. Examine the clustering evaluation and final results.

### Option 2 — Local Jupyter Notebook

Install the required dependencies:

```bash
pip install pandas numpy matplotlib seaborn scikit-learn notebook
```

Launch Jupyter Notebook:

```bash
jupyter notebook
```

The notebook uses `google.colab.files.upload()`, so this step must be replaced with a local file-loading procedure when running outside Google Colab.

## 8. Limitations

- The analysis is based on a small educational dataset.
- K-Means assumes distance-based cluster structures.
- Clustering results depend on preprocessing and the chosen number of clusters.
- The selected k = 3 does not maximize the measured Silhouette Score.
- Species labels are used only for post-clustering comparison.
- The notebook demonstrates exploratory clustering rather than a production-ready botanical classification system.

## 9. Potential Applications

The techniques explored in this project can support:

- Exploratory Data Analysis.
- Customer segmentation.
- Pattern discovery.
- Unsupervised Machine Learning.
- Feature exploration.
- Educational clustering experiments.

## 10. Conclusion

This project demonstrates a complete introductory data mining workflow using the Iris dataset.

Through data preparation, exploratory visualization, feature standardization, and K-Means clustering, the analysis identifies meaningful patterns among botanical observations.

The results show that Iris-setosa is clearly distinguishable, while Iris-versicolor and Iris-virginica share more similar measurement characteristics.

The experiment also highlights the importance of comparing clustering metrics with domain-specific interpretation when selecting model configurations.

---

## Author

**Data Engineer Luis Barahona**

Mexican Data Engineer and 2026 graduate of Universidad del Caribe, interested in Data Engineering, Data Science, Machine Learning, Artificial Intelligence, and continuous professional development.

## Contact

| Platform | Contact |
|:---|:---|
| Email | [190300395@ucaribe.edu.mx](mailto:190300395@ucaribe.edu.mx) |
| GitHub | [github.com/LuisBarahonaMX](https://github.com/LuisBarahonaMX) |
| LinkedIn | [linkedin.com/in/luis-barahona-mx](https://www.linkedin.com/in/luis-barahona-mx/) |
| Instagram | [@luisbarahonamx](https://www.instagram.com/luisbarahonamx/) |
| X | [@luisbarahonaMX](https://x.com/luisbarahonaMX) |
| Website | [SIKO AI Platform](https://sikoai.web.app/) |
