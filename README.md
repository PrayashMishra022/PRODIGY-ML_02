# K-Means Clustering: Customer Segmentation

This project applies K-Means Clustering to segment customers based on two key metrics: Annual Income and Spending Score. The goal is to group customers into distinct clusters that help identify patterns and behaviors, such as high-spending groups or low-income segments. The insights derived from this clustering can be used to enhance business strategies, optimize customer targeting, and personalize marketing campaigns.

## Methodology

1. **Data Loading and Preparation**
    * Import and inspect the dataset, `Mall_Customers.csv`, for consistency.
    * Check and handle missing values if necessary.
    * Rename relevant columns (`Annual Income (k$)` and `Spending Score (1-100)`) for clarity and extract them for analysis.

2. **Data Standardization**
    * Standardize features using `StandardScaler` to remove biases caused by differing scales of variables.

3. **Optimal Cluster Identification**
    * Use the Elbow Method to determine the ideal number of clusters (k).
    * Generate a plot of inertia values for cluster counts ranging from 1 to 10.
    * Choose the optimal k based on the "elbow point" where the rate of inertia reduction slows down.

4. **Clustering with K-Means**
    * Apply K-Means clustering using the optimal k (e.g., k=5) to segment the customers.
    * Assign a cluster label to each customer based on their annual income and spending score.

5. **Visualization of Results**
    * Create a scatter plot to visualize the clusters with each point representing a customer.
    * Color points by cluster and annotate with unique identifiers (customer indices) for better understanding.
    * The plot clearly shows the segregation of customers into distinct groups based on their spending behavior and income levels.

6. **Saving Clustered Data**
    * Save the final dataset, including cluster labels, to `Customer_Clusters_Annual_Income_Spending.csv` for further analysis.

## Key Insights

This approach provides a clear grouping of customers, enabling businesses to understand different spending behaviors. The clusters can be used for targeted marketing, loyalty programs, and resource optimization.

## Technologies Used

* Python
* Libraries: Pandas, NumPy, Matplotlib, Seaborn, Scikit-learn

**Feel free to use this repository for your own clustering tasks and adapt it for your datasets and business needs!**
