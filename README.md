# Clustering-and-PCA

## 1. K-means clustering of image pixels
Usage: 
K-means clustering can be highly useful for image pixel analysis by segmenting an image into clusters based on pixel intensities or color. This technique assigns each pixel to a cluster with the nearest mean color value, effectively grouping similar pixels togethe

## 2. Hierarchical Clustering for Breast Cancer 

Hierarchical clustering is a technique that groups data points into a tree-like structure based on their similarity, revealing multilevel groupings in the data. 

The three common linkage methods are 
1. Complete linkage (maximizing distance between clusters)
2. Single linkage (minimizing distance)
3. Average linkage (using the average distance)
each defining cluster similarity differently to influence the shape and size of the resulting clusters.

## K-means Clustering vs Hierarchical Clustering:

**K-means Clustering**
1. Large Datasets: K-means is generally more scalable to **large datasets** than hierarchical clustering.
2. Well-Separated Clusters: It works well when clusters have a spherical shape and are relatively well separated.
3. Flat Clustering Requirement: K-means provides a flat clustering structure, which is useful when **the number of clusters is known** or can be estimated.
**Hierarchical Clustering**
1. Small to Medium Datasets: More suitable for **smaller datasets** due to its higher computational complexity.
2. Unknown Number of Clusters: Ideal when the number of clusters is not known beforehand, as it provides a dendrogram which can be used to decide the number of clusters.
3. No Need for Pre-specifying Clusters: **Does not require the number of clusters to be specified in advance**, unlike K-means.



## 3. Eigen Decomposition and PCA

## PCA
Goal: 
The algorithm proceeds by first finding the component having **maximal variance**

Usage:
PCA should be used mainly for variables which are strongly correlated
- Reduce the number of features but cannot identify the unimportant ones that can be ignored, and
- Ensure that the features of the data are independent of one another even if the features become less interpretable

## What do eigenvalues represent in statistics?
The term **eigenvalues** refers to the variance of a data matrix. 
While a common term in matrix algebra, in statistics, eigenvalues are commonly discussed in factor analysis. 
Here, an eigenvalue represents the amount of variance contained by a factor.

## How PCA uses this concept of eigendecomposition?
Say, we have a dataset with ‘n’ predictor variables. 
We center the predictors to their respective means and then get an n x n covariance matrix. 
This covariance matrix is then decomposed into eigenvalues and eigenvectors.
<img width="620" alt="Screenshot 2024-01-08 at 10 36 26 PM" src="https://github.com/ColleenJung/Clustering-and-PCA/assets/119357849/814e6416-80ed-4c93-9c3b-1565b299b9f3">

1. Measures how each variable is associated with one another using a **Covariance matrix**
2. Understands the directions of the spread of our data using **Eigenvectors**
3. Brings out the relative importance of these directions using **Eigenvalues**
<img width="422" alt="Screenshot 2024-01-08 at 10 36 44 PM" src="https://github.com/ColleenJung/Clustering-and-PCA/assets/119357849/0cd42b13-7299-4d06-9a69-e7ff281ae6b3">

The eigenvectors can now be sorted by the eigenvalues in descending order to provide a ranking of the components or axes of the new subspace for matrix A.
In the above output, eigenvectors give the PCA components and eigenvalues give the explained variances of the components. As we have 3 predictors here, we get 3 eigenvalues.

The eigenvectors can now be sorted by the eigenvalues in descending order to provide a ranking of the components or axes of the new subspace for matrix A.
If there are eigenvalues close to zero, they represent components that may be discarded.

Let’s check the explained variance ratio of the first component as:

explained variance of 1st component / (total of all explained variances)
<img width="722" alt="Screenshot 2024-01-08 at 10 37 44 PM" src="https://github.com/ColleenJung/Clustering-and-PCA/assets/119357849/a6cf3d41-0c42-483b-aae3-8541c11ad008">

We see that the first component is enough to explain up to 99% variance in the data. So, we can now project our data into a 4x1 matrix instead of a 4x3 matrix, thereby reducing the dimension of data, of course with a minor loss in information.

