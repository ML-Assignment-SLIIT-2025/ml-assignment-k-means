# K-Means Clustering

## Overview
This repository applies K-Means clustering, an unsupervised learning algorithm, to group customers from the Telco Customer Churn dataset into meaningful segments based on their features. It includes extensive visualizations, statistical tests, and validation metrics to assess whether the clusters are distinct and representative of customer groups. The analysis names clusters dynamically and evaluates their significance for business insights.

## Dataset
- **Input File**: `X_preprocessed.csv` (features)
- **Note**: `y_preprocessed.csv` (Churn) is used only for post hoc evaluation, not for clustering.

## Contents
- `K_Means_Churn.ipynb`: Jupyter notebook for K-Means clustering, visualization, validation, and interpretation.

## Steps
1. **Data Loading**: Loads preprocessed features (`X_preprocessed.csv`) and target (`y_preprocessed.csv`).
2. **Cluster Selection**: Uses the Elbow Method and Silhouette Scores to determine the optimal number of clusters (`k=3` used in this case).
3. **Clustering**: Applies K-Means with `k=3`, assigning customers to clusters.
4. **Visualization**:
   - Elbow Curve and Silhouette Score plots for `k` selection.
   - Scatter plot with centroids (tenure vs. MonthlyCharges).
   - PCA plot showing cluster separation in 2D.
   - Boxplots for numerical features (`tenure`, `MonthlyCharges`, `TotalCharges`).
   - Bar plots for top 5 categorical features (e.g., `Contract_Month-to-month`).
   - Silhouette plot for cluster quality.
   - Heatmap of mean feature values across clusters.
   - Churn distribution bar plot.
5. **Validation**:
   - Silhouette Score (average and per-point) to measure cluster separation.
   - Davies-Bouldin Index for cluster distinctness.
   - ANOVA tests for numerical features.
   - Chi-Square tests for categorical features.
6. **Interpretation**: Names clusters based on `tenure`, `MonthlyCharges`, and `Churn` (e.g., "Short-Term High-Cost High-Risk") and assesses their meaningfulness.

## Requirements
- Python 3.11
- Libraries: `numpy`, `pandas`, `matplotlib`, `seaborn`, `sklearn`, `scipy`
- Install dependencies:
  ```bash
  pip install numpy pandas matplotlib seaborn scikit-learn scipy
  ```
  
## Usage
- Clone the repository:
- Upload `X_preprocessed.csv` and `y_preprocessed.csv` to your environment.
- Open and run `K_Means_Churn.ipynb`.

## Outputs

### Metrics:
- Silhouette Score (e.g., 0.45) and Davies-Bouldin Index (e.g., 0.8) for cluster quality.
- ANOVA and Chi-Square p-values for feature distinctness.

### Visualizations:
- Elbow Curve: Identifies optimal k.
- Silhouette Plot: Shows separation per cluster.
- Scatter Plot: Clusters with centroids in tenure vs. MonthlyCharges space.
- PCA Plot: 2D projection with explained variance.
- Boxplots: Distribution of numerical features by cluster.
- Bar Plots: Categorical feature distributions.
- Heatmap: Mean feature differences across clusters.
- Churn Distribution: Proportion of churn by cluster.

### Interpretation
- Descriptive cluster names and business insights.

### Assessment
- Summary of cluster meaningfulness.

## Cluster Validation
- Silhouette Score: >0.5 indicates well-separated clusters; 0.2-0.5 is moderate; <0.2 suggests overlap.
- Davies-Bouldin Index: <1.0 suggests good separation; higher values indicate potential overlap.
- Statistical Tests: P-values <0.05 for ANOVA (numerical) and Chi-Square (categorical) confirm distinct groups.
