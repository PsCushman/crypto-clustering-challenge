# Crypto Clustering Challenge

This challenge focuses on unsupervised machine learning. There are two jupyter notebooks. One followed the assigment direction almost exactly and the other I created two functions. The first, caluclated the interia values and put them into a DataFrame to be used for plotting the elbow curve. The other  took the best K number and created a DataFrame with the clustering values added to the orginal as to be used for plotting. Both notebooks are included here. 

![Screen Shot 2023-07-29 at 2 39 21 PM](https://github.com/PsCushman/crypto-clustering-challenge/assets/122395437/81ed3e1c-977d-4eb2-9118-46235f4c87d9)

# Instructions

Prepare the Data
Use the StandardScaler() module from scikit-learn to normalize the data from the CSV file.

Create a DataFrame with the scaled data and set the "coin_id" index from the original DataFrame as the index for the new DataFrame.

![Screen Shot 2023-07-29 at 2 39 59 PM](https://github.com/PsCushman/crypto-clustering-challenge/assets/122395437/2ee25c91-e23b-4bed-839d-ef7f7258cf4a)

Find the Best Value for k Using the Original Scaled DataFrame
Use the elbow method to find the best value for k using the following steps:

Create a list with the number of k values from 1 to 11.
Create an empty list to store the inertia values.
Create a for loop to compute the inertia with each possible value of k.
Create a dictionary with the data to plot the elbow curve.
Plot a line chart with all the inertia values computed with the different values of k to visually identify the optimal value for k.

![Screen Shot 2023-07-29 at 2 40 57 PM](https://github.com/PsCushman/crypto-clustering-challenge/assets/122395437/6a7b37cf-6f57-474c-9929-6284d81357a6)

Answer the following question in your notebook: What is the best value for k? **4**

Cluster Cryptocurrencies with K-means Using the Original Scaled Data
Use the following steps to cluster the cryptocurrencies for the best value for k on the original scaled data:

![Screen Shot 2023-07-29 at 2 41 40 PM](https://github.com/PsCushman/crypto-clustering-challenge/assets/122395437/c14b663a-e48e-4ecc-8907-01a13635376c)

Initialize the K-means model with the best value for k.
Fit the K-means model using the original scaled DataFrame.
Predict the clusters to group the cryptocurrencies using the original scaled DataFrame.


Create a copy of the original data and add a new column with the predicted clusters.
Create a scatter plot using hvPlot as follows:
Set the x-axis as "PC1" and the y-axis as "PC2".
Color the graph points with the labels found using K-means.
Add the "coin_id" column in the hover_cols parameter to identify the cryptocurrency represented by each data point.

![Screen Shot 2023-07-29 at 2 42 46 PM](https://github.com/PsCushman/crypto-clustering-challenge/assets/122395437/ee0665fe-04b5-4017-abd3-00ccfba7d865)

Optimize Clusters with Principal Component Analysis
Using the original scaled DataFrame, perform a PCA and reduce the features to three principal components.

Retrieve the explained variance to determine how much information can be attributed to each principal component and then answer the following question in your notebook:

![Screen Shot 2023-07-29 at 2 43 21 PM](https://github.com/PsCushman/crypto-clustering-challenge/assets/122395437/7d674452-c9db-422f-bb71-92c744c46440)

What is the total explained variance of the three principal components? **0.8950**

Create a new DataFrame with the PCA data and set the "coin_id" index from the original DataFrame as the index for the new DataFrame.

Find the Best Value for k Using the PCA Data
Use the elbow method on the PCA data to find the best value for k using the following steps:

Create a list with the number of k-values from 1 to 11.
Create an empty list to store the inertia values.
Create a for loop to compute the inertia with each possible value of k.
Create a dictionary with the data to plot the Elbow curve.
Plot a line chart with all the inertia values computed with the different values of k to visually identify the optimal value for k.

![Screen Shot 2023-07-29 at 2 45 38 PM](https://github.com/PsCushman/crypto-clustering-challenge/assets/122395437/a3a1c8ec-86e1-4c67-9a32-0db2ac4faa43)

Answer the following question in your notebook:
What is the best value for k when using the PCA data? **4**
Does it differ from the best k value found using the original data? **NO**

Cluster Cryptocurrencies with K-means Using the PCA Data
Use the following steps to cluster the cryptocurrencies for the best value for k on the PCA data:

Initialize the K-means model with the best value for k.
Fit the K-means model using the PCA data.
Predict the clusters to group the cryptocurrencies using the PCA data.
Create a copy of the DataFrame with the PCA data and add a new column to store the predicted clusters.

![Screen Shot 2023-07-29 at 2 46 01 PM](https://github.com/PsCushman/crypto-clustering-challenge/assets/122395437/f132075d-ced7-480b-8757-3fb36adf576b)

Create a scatter plot using hvPlot as follows:
Set the x-axis as "PCA_1" and the y-axis as "PCA_2".
Color the graph points with the labels found using K-means.
Add the "coin_id" column in the hover_cols parameter to identify the cryptocurrency represented by each data point.

![Screen Shot 2023-07-29 at 2 46 37 PM](https://github.com/PsCushman/crypto-clustering-challenge/assets/122395437/8fd0f793-ae2a-49be-8afd-a257e4d26b00)

![Screen Shot 2023-07-29 at 2 46 58 PM](https://github.com/PsCushman/crypto-clustering-challenge/assets/122395437/97e9688b-2656-4412-9f6e-1e3a9fa26523)

Answer the following question:
What is the impact of using fewer features to cluster the data using K-Means? **Answer: The PCA Data Looks marginally better. While the clusters are a little better defined, once you look at the graph when it shares the same scale, it is not that much different. However, the outliers are more easily decernable and look more like outliers.**
