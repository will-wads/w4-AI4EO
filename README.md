# About
This repository goes over some techniques for unsupervised classification between two categories. In this case differentiating between sea ice and lead. A lead refers to a large crack in sea ice, which creates an opening/exposes sea water underneath, these are vital for the creation of more sea ice, so their observations are crucial. 


## Introduction to Unsupervised Learning Methods
# Introduction to K-means Clustering
K-means clustering is a type of unsupervised learning algorithm used for partitioning a dataset into a set of k groups (or clusters), where k represents the number of groups pre-specified by the analyst. It classifies the data points based on the similarity of the features of the data {cite}macqueen1967some. The basic idea is to define k centroids, one for each cluster, and then assign each data point to the nearest centroid, while keeping the centroids as small as possible.

# Why K-means for Clustering?
K-means clustering is particularly well-suited for applications where:

The structure of the data is not known beforehand: K-means doesn’t require any prior knowledge about the data distribution or structure, making it ideal for exploratory data analysis.
Simplicity and scalability: The algorithm is straightforward to implement and can scale to large datasets relatively easily.
Key Components of K-means
Choosing K: The number of clusters (k) is a parameter that needs to be specified before applying the algorithm.
Centroids Initialization: The initial placement of the centroids can affect the final results.
Assignment Step: Each data point is assigned to its nearest centroid, based on the squared Euclidean distance.
Update Step: The centroids are recomputed as the center of all the data points assigned to the respective cluster.
# The Iterative Process of K-means
The assignment and update steps are repeated iteratively until the centroids no longer move significantly, meaning the within-cluster variation is minimised. This iterative process ensures that the algorithm converges to a result, which might be a local optimum.

Advantages of K-means
Efficiency: K-means is computationally efficient.
Ease of interpretation: The results of k-means clustering are easy to understand and interpret.


## Introduction to Gaussian Mixture Models
Gaussian Mixture Models (GMM) are a probabilistic model for representing normally distributed subpopulations within an overall population. The model assumes that the data is generated from a mixture of several Gaussian distributions, each with its own mean and variance {cite}reynolds2009gaussian, mclachlan2004finite. GMMs are widely used for clustering and density estimation, as they provide a method for representing complex distributions through the combination of simpler ones.

# Why Gaussian Mixture Models for Clustering?
Gaussian Mixture Models are particularly powerful in scenarios where:

Soft clustering is needed: Unlike K-means, GMM provides the probability of each data point belonging to each cluster, offering a soft classification and understanding of the uncertainties in our data.
Flexibility in cluster covariance: GMM allows for clusters to have different sizes and different shapes, making it more flexible to capture the true variance in the data.
# Key Components of GMM
Number of Components (Gaussians): Similar to K in K-means, the number of Gaussians (components) is a parameter that needs to be set.
Expectation-Maximization (EM) Algorithm: GMMs use the EM algorithm for fitting, iteratively improving the likelihood of the data given the model.
Covariance Type: The shape, size, and orientation of the clusters are determined by the covariance type of the Gaussians (e.g., spherical, diagonal, tied, or full covariance).
# The EM Algorithm in GMM
The Expectation-Maximization (EM) algorithm is a two-step process:

Expectation Step (E-step): Calculate the probability that each data point belongs to each cluster.
Maximization Step (M-step): Update the parameters of the Gaussians (mean, covariance, and mixing coefficient) to maximize the likelihood of the data given these assignments.
This process is repeated until convergence, meaning the parameters do not significantly change from one iteration to the next.

# Advantages of GMM
Soft Clustering: Provides a probabilistic framework for soft clustering, giving more information about the uncertainties in the data assignments.
Cluster Shape Flexibility: Can adapt to ellipsoidal cluster shapes, thanks to the flexible covariance structure


## data sourced
The data used in this project came from the Sentinel 2 and Sentinel 3 satellites, due to the size of the folders they were not included, however they can be found online at the readers discretion: 

Sentinel 2:
S2A_MSIL1C_20190301T235611_N0207_R116_T01WCU_20190302T014622.SAFE

Sentinel 3:
S3A_SR_2_LAN_SI_20190307T005808_20190307T012503_20230527T225016_1614_042_131______LN3_R_NT_005.SEN3

# Acknowledgements
This was completed for the week 4 assignment of the "GEOL0069" module, "AI for earth observations" and is based off material provided by said module.
