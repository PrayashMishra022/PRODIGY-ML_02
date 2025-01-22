import kagglehub

# Download latest version
path = kagglehub.dataset_download("vjchoudhary7/customer-segmentation-tutorial-in-python")

print("Path to dataset files:", path)

# Import necessary libraries
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
from sklearn.cluster import KMeans
from sklearn.preprocessing import StandardScaler

# Load the dataset using pandas 
data = pd.read_csv(path + '/Mall_Customers.csv')

# Display the first few rows of the dataset
print("Dataset preview:")
print(data.head())

# Check for missing values
print("\nChecking for missing values:")
print(data.isnull().sum())

# Rename columns for consistency
data = data.rename(columns={"Annual Income (k$)": "Annual_Income", "Spending Score (1-100)": "Spending_Score"})

# Select relevant features for clustering
features = data[["Annual_Income", "Spending_Score"]]

# Standardize the data for clustering
scaler = StandardScaler()
scaled_features = scaler.fit_transform(features)

# Determine the optimal number of clusters using the Elbow method
inertia = []
k_range = range(1, 11)

for k in k_range:
    kmeans = KMeans(n_clusters=k, random_state=42)
    kmeans.fit(scaled_features)
    inertia.append(kmeans.inertia_)

# Plot the Elbow curve
plt.figure(figsize=(8, 5))
plt.plot(k_range, inertia, marker='o')
plt.title('Elbow Method for Optimal k')
plt.xlabel('Number of Clusters (k)')
plt.ylabel('Inertia')
plt.xticks(k_range)
plt.grid()
plt.show()

# Based on the Elbow plot, choose the optimal number of clusters (e.g., k=5)
k_optimal = 5
kmeans = KMeans(n_clusters=k_optimal, random_state=42)
clusters = kmeans.fit_predict(scaled_features)

# Add the cluster labels to the original dataset
data['Cluster'] = clusters

# Visualize the clusters with enhanced clarity
plt.figure(figsize=(12, 10))
sns.scatterplot(x="Annual_Income", y="Spending_Score", hue="Cluster", data=data, palette="Set2", s=200, edgecolor="black", alpha=0.9)

# Annotate each point with customer IDs or indices
for i in range(len(data)):
    plt.text(x=data["Annual_Income"][i] + 0.5, y=data["Spending_Score"][i] + 0.5, 
             s=str(i), fontsize=8, color='black', alpha=0.7)

plt.title('Customer Segments with Annotations', fontsize=18)
plt.xlabel('Annual Income (k$)', fontsize=14)
plt.ylabel('Spending Score (1-100)', fontsize=14)
plt.legend(title='Cluster', fontsize=12, title_fontsize=14, loc='upper right')
plt.grid(visible=True, linestyle='--', alpha=0.6)
plt.show()

# Save the clustered data to a new CSV file
data.to_csv('Customer_Clusters_Annual_Income_Spending.csv', index=False)
print("Clustered data saved to 'Customer_Clusters_Annual_Income_Spending.csv'")
