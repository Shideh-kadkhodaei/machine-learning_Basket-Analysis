# Customer Segmentation Using K-Means Clustering

## 📌 Project Overview

This project applies unsupervised machine learning techniques to segment mall customers based on their annual income and spending behavior.

Using the **K-Means clustering algorithm**, the project identifies groups of customers with similar characteristics. These segments can help businesses better understand customer behavior and support data-driven marketing strategies.

## 🎯 Objectives

- Explore and understand customer demographic and spending data.
- Perform exploratory data analysis (EDA) and visualization.
- Preprocess and scale numerical features for clustering.
- Determine the appropriate number of clusters using the Elbow Method and Silhouette Score.
- Apply K-Means clustering to segment customers.
- Analyze cluster characteristics and customer profiles.
- Visualize customer segments and cluster centroids.

## 📂 Dataset

The project uses `Mall_Customers.csv`, which contains **200 customer records** and the following features:

| Feature | Description |
|---|---|
| `CustomerID` | Unique customer identifier |
| `Gender` | Customer gender |
| `Age` | Customer age |
| `Annual Income (k$)` | Annual income in thousands of dollars |
| `Spending Score (1-100)` | Spending score on a scale of 1 to 100 |

## 🛠️ Technologies Used

- **Python**
- **Pandas** — data manipulation and analysis
- **NumPy** — numerical operations
- **Matplotlib** — data visualization
- **Seaborn** — statistical visualization
- **Scikit-learn** — feature scaling and clustering
- **Jupyter Notebook** — interactive development environment

## 🔍 Project Workflow

### 1. Exploratory Data Analysis (EDA)

The dataset is examined to understand its structure and characteristics.

Analysis includes:
- Summary statistics and unique value counts.
- Missing-value checks.
- Gender and age distributions.
- Annual income and spending score distributions.
- Outlier inspection using boxplots.
- Correlation analysis using a heatmap.
- Pairwise relationships between numerical features.

### 2. Data Preprocessing

The following preprocessing steps are performed:

- Rename columns for easier access and readability.
- Fill missing numerical values with their median.
- Fill missing gender values with the mode.
- Encode the gender variable using one-hot encoding.
- Select annual income and spending score as the clustering features.
- Standardize the selected features using `StandardScaler`.

The `CustomerID` column is excluded from clustering because it is an identifier rather than a meaningful behavioral feature.

### 3. Data Storytelling and Visualization

Several visualizations are created to explore customer behavior:

- Annual income versus spending score.
- Spending score distribution across age groups.
- Average age, income, and spending score by gender.
- Income and spending patterns by gender.
- Customer behavior across different age groups.
- Relationships between age, income, and spending score.

These visualizations provide context for interpreting the customer segments.

### 4. Selecting the Number of Clusters

Two methods are used to evaluate the number of clusters.

**Elbow Method**

The inertia (within-cluster sum of squares) is calculated for different values of K to examine how clustering compactness changes as the number of clusters increases.

**Silhouette Score**

Silhouette scores are calculated for K values from 2 to 7 to evaluate how well-separated the clusters are.

The highest tested silhouette score is **0.5547 at K = 5**, so five clusters are selected for the final model.

### 5. K-Means Clustering

The final K-Means model is configured with:

- Number of clusters: `5`
- Random state: `42`
- Number of initializations: `10`

The model groups customers using standardized annual income and spending score values. The resulting cluster labels are added to the dataset.

### 6. Cluster Profiling

The project calculates the average age, annual income, and spending score for each cluster, along with the number of customers in each group.

The five clusters can be interpreted broadly as:

| Cluster | Customer Segment | Average Annual Income (k$) | Average Spending Score |
|---|---|---:|---:|
| 0 | Average income, moderate spending | 55.30 | 49.52 |
| 1 | High income, high spending | 86.54 | 82.13 |
| 2 | Low income, high spending | 25.73 | 79.36 |
| 3 | High income, low spending | 88.20 | 17.11 |
| 4 | Low income, low spending | 26.30 | 20.91 |

These labels are descriptive interpretations based on cluster averages, not predefined customer categories.

### 7. Final Visualization

A scatter plot displays the five customer segments using annual income and spending score. Cluster centroids are also plotted to show the center of each group.

## 📊 Key Findings

The clustering results reveal several distinct customer profiles:

- **High-income, high-spending customers:** Potentially valuable customers for premium offers and loyalty programs.
- **High-income, low-spending customers:** May respond to targeted promotions or engagement strategies.
- **Low-income, high-spending customers:** Demonstrate high spending scores despite lower annual incomes.
- **Low-income, low-spending customers:** Have lower average income and spending scores.
- **Moderate-income, moderate-spending customers:** Represent the largest segment in this analysis.

These findings can help businesses develop more targeted marketing and customer engagement strategies.

## 🚀 Getting Started

### Prerequisites

Install the required libraries:

```bash
pip install numpy pandas matplotlib seaborn scikit-learn jupyter
```

### Run the Project

1. Clone or download the repository.
2. Place `Mall_Customers.csv` in the project directory.
3. Open the Jupyter Notebook.
4. Run the notebook cells in order.

```bash
jupyter notebook
```

## 📁 Project Structure

```text
Customer-Segmentation/
│
├── Mall_Customers.csv
├── Machine Learning in Python Mini Project4.ipynb
└── README.md
```

*Adjust the notebook filename above to match the actual filename in your repository.*

## 🔮 Future Improvements

- Compare K-Means with other clustering algorithms, such as DBSCAN and hierarchical clustering.
- Evaluate cluster stability using different initializations and feature combinations.
- Explore the effect of including age in the clustering process.
- Develop an interactive dashboard for customer segment exploration.
- Translate customer segments into more detailed marketing recommendations.
