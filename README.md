# CryptoClustering
This analysis employs unsupervised learning in Python to predict price changes among various cryptocurrencies.

### Prepare the Data
The data from the CSV file in the Resources folder is normalized using sklearn's StandardScaler.fit_transform() function. A pandas DataFrame is created to store the scaled data.

### Find the Best Value for k Using the Original Scaled DataFrame
The elbow method is ued to find the best value for k, as follows:

- Create a list with the number of k values from 1 to 11.
- Create an empty list to store the inertia values.
- Create a for loop to compute the inertia with each possible value of k.
- Create a dictionary with the data to plot the elbow curve.
- Plot a line chart with all the inertia values computed with the different values of k to visually identify the optimal value for k.

### Cluster Cryptocurrencies with K-means Using the Original Scaled Data
The cryptocurrencies are grouped in k clusters, as follows:

- Initialize a K-means model from the sklearn library.
- Fit the K-means model using the original scaled DataFrame.
- Predict the clusters to group the cryptocurrencies using the original scaled DataFrame.
- Create a copy of the original data and add a new column with the predicted clusters.
- Create a scatter plot with the x-axis as "PCA1" and the y-axis as "PCA2", graph points colored according to the labels found using K-means, and coin ID as hover columns.

### Optimize Clusters with Principal Component Analysis (PCA)
Using the original scaled DataFrame, PCA is performed to reduce the number of features. We retrieve the explained variance using sklearn's PCA.expalined_variance_ratio_ function. 

The the elbow method is applied to the PCA data to find the best value for k, and the cryptocurrencies are again clustered, this time using the PCA data.  

A new scatter plot is created with the following characteristics:
- "price_change_percentage_24h" as the x-axis and "price_change_percentage_7d" as the y-axis.
- Graph points colored with the labels found using K-means.
- Coin ID in hover_cols 
