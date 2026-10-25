# Customer Segmentation using K-Means Clustering

![Python Version](https://img.shields.io/badge/python-3.x-blue.svg)
![Library](https://img.shields.io/badge/scikit--learn-clustering-orange.svg)
![License](https://img.shields.io/badge/license-MIT-green.svg)

An end-to-end Machine Learning mini-project focusing on **unsupervised customer segmentation** using the K-Means clustering algorithm. This project analyzes customer data from a retail mall to identify distinct purchasing behaviors and segments based on annual income and spending scores, enabling targeted marketing strategies.

---

## 📊 Dataset Overview

The project uses the **Mall Customers** dataset (`Mall_Customers.csv`), which contains 200 records with the following features:
* **CustomerID:** Unique ID assigned to the customer.
* **Gender:** Demographic category (Male / Female).
* **Age:** Customer age (ranging from 18 to 70 years).
* **Annual Income (k$):** Customer's annual income in thousands of dollars.
* **Spending Score (1-100):** Score assigned by the mall based on customer behavior and purchasing habits.

---

## 🛠️ Project Workflow

1. **Data Loading & Cleaning:**
   * Loaded the dataset, inspected structural integrity, and verified missing values.
   * Cleaned and renamed column headers to standard snake_case formats.

2. **Exploratory Data Analysis (EDA):**
   * Generated distribution plots, histograms, and boxplots to understand demographic and financial distributions.
   * Created correlation heatmaps and bivariate pairplots (segmented by gender and age groups).

3. **Feature Engineering & Preprocessing:**
   * Encoded categorical variables (`Gender`) using one-hot encoding.
   * Standardized numerical features (`Annual Income` and `Spending Score`) using `StandardScaler` to ensure equal variance weighting during clustering.

4. **Model Training & Evaluation (K-Means):**
   * **Elbow Method:** Evaluated inertia across $K \in [1, 10]$ to locate the optimal inflection point.
   * **Silhouette Analysis:** Calculated silhouette scores for $K=2$ through $K=7$, identifying **$K=5$** as the optimal cluster count (highest silhouette score $\approx 0.55$).
   * Fitted the final K-Means model (`n_clusters=5`, `random_state=42`).

5. **Cluster Profiling & Visualization:**
   * Mapped cluster labels back to the original dataframe and inverse-transformed centroids.
   * Visualized the 5 distinct customer segments alongside their cluster centers.

---

## 📁 Repository Structure
```text
├── code.ipynb          # Jupyter Notebook containing the full end-to-end workflow
├── Mall_Customers.csv  # Dataset used for clustering analysis
└── README.md           # Project documentation
