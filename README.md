# PRODIGY-ML_02
K-Means Clustering: Customer Segmentation

Overview

This project applies K-Means Clustering to segment customers based on two key metrics: Annual Income and Spending Score. The goal is to group customers into distinct clusters that help identify patterns and behaviors, such as high-spending groups or low-income segments. The insights derived from this clustering can be used to enhance business strategies, optimize customer targeting, and personalize marketing campaigns.

Methodology

1. Data Loading and Preparation

The dataset, Mall_Customers.csv, is imported and inspected for consistency.

Missing values are checked and handled if necessary.

Relevant columns (Annual Income (k$) and Spending Score (1-100)) are renamed for clarity and extracted for analysis.

2. Data Standardization

Features are standardized using StandardScaler to remove biases caused by differing scales of variables.

3. Optimal Cluster Identification

The Elbow Method is used to determine the ideal number of clusters (k).

A plot of inertia values for cluster counts ranging from 1 to 10 is generated, and the optimal k is chosen based on the "elbow point" where the rate of inertia reduction slows down.

4. Clustering with K-Means

Using the optimal k (e.g., k=5), K-Means clustering is applied to segment the customers.

Each customer is assigned a cluster label based on their annual income and spending score.

5. Visualization of Results

A scatter plot is created to visualize the clusters with each point representing a customer.

Points are colored by cluster and annotated with unique identifiers (customer indices) for better understanding.

The plot clearly shows the segregation of customers into distinct groups based on their spending behavior and income levels.

6. Saving Clustered Data

The final dataset, including cluster labels, is saved to Customer_Clusters_Annual_Income_Spending.csv for further analysis.

Key Insights

This approach provides a clear grouping of customers, enabling businesses to understand different spending behaviors.

The clusters can be used for targeted marketing, loyalty programs, and resource optimization.

Technologies Used

Python

Libraries: Pandas, NumPy, Matplotlib, Seaborn, Scikit-learn

Feel free to use this repository for your own clustering tasks and adapt it for your datasets and business needs!

