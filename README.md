# Customer Segmentation and Clustering

## Project Overview
This project focuses on customer segmentation using clustering techniques. Customer profiles were built using transactional and profile data, followed by applying clustering algorithms to identify distinct customer segments. Metrics such as the Davies-Bouldin Index (DB Index) were calculated to evaluate clustering performance, and the results were visualized for better interpretability.

---

## Dataset
### Input Files:
1. **Customers.csv**: Contains customer profile information such as demographic and tenure details.
2. **Transactions.csv**: Includes transaction data, such as transaction ID, category, and total value of purchases.

### Output Files:
- **Lookalike.csv**: A mapping of customers to their top 3 lookalikes based on similarity.

---

## Workflow

### 1. Data Preprocessing
- Merged `Customers.csv` and `Transactions.csv` to create a comprehensive dataset.
- Cleaned and handled missing values.

### 2. Feature Engineering
Created the following customer profile features:
- **total_spend**: Total spend by the customer.
- **avg_order_value**: Average order value.
- **purchase_frequency**: Number of transactions.
- **favorite_category**: The most frequently purchased category.
- **Tenure**: Customer tenure in years.

Normalized numerical features using `StandardScaler` to ensure uniform scaling:
- `total_spend`, `avg_order_value`, `purchase_frequency`, `Tenure`.

### 3. Clustering
- Applied **K-Means** clustering with different numbers of clusters (k = 2 to 10).
- Evaluated the clustering results using the **Davies-Bouldin Index (DB Index)** and selected the optimal number of clusters.
- Visualized the clusters using:
  - Scatter plots of cluster assignments.
  - Pair plots to explore feature relationships within clusters.

### 4. Evaluation Metrics
- Calculated the DB Index for clustering evaluation.
- Assessed intra-cluster similarity and inter-cluster separation.

---

## Results
- **Optimal Number of Clusters**: _[Insert Number]_  
- **DB Index**: _[Insert Value]_  

Clusters were visualized, showing distinct segments with significant separations.

---

## Code Structure

### Key Files:
1. **clustering_analysis.py**
   - Contains the implementation of clustering, DB Index calculation, and visualization.
2. **Lookalike.csv**
   - Mapping of customers to their top 3 similar customers based on similarity scores.
3. **README.md**
   - This file.

### Functions:
- `get_top_lookalikes(customer_id, similarity_df, top_n=3)`: Generates top N similar customers for a given customer.
- `calculate_db_index(features, cluster_labels)`: Computes the Davies-Bouldin Index.
- `plot_clusters(features, cluster_labels)`: Visualizes clustering results.

---

## Libraries Used
- `pandas`
- `numpy`
- `sklearn`
  - `StandardScaler`
  - `KMeans`
  - `metrics`
- `matplotlib`
- `seaborn`

---

## How to Run the Code
1. Install required libraries:
   ```bash
   pip install pandas numpy scikit-learn matplotlib seaborn
   ```
2. Place `Customers.csv` and `Transactions.csv` in the project directory.
3. Run the script:
   ```bash
   python ML.ipynb
   ```
4. Outputs, including visualizations and `Lookalike.csv`, will be saved in the project directory.

---
