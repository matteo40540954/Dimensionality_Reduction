# Introduction to Dimensionality reduction 

This was a small project for the class "Introduction to Python" in which: 
1) i had to use Object oriented programming and only matplotlib and numpy to compute Principal Component Analysis (PCA) and Stochastic Neighbor Embedding (SNE)
2) compare the results of PCA and SNE with tPCA and tSNE 

MNIST Dataset (60000 Handwritten digit images from 0 to 9 of 28×28 px → 784 features per sample) in which we randomly selected 6000 digits.  

# Dimensionality Reduction

Real-world data is often high-dimensional (think 784 pixel values per image, or thousands of brain voxels in an fMRI scan) and difficult to interpret. Dimensionality reduction maps this data into a low-dimensional space (typically 2D or 3D called Embedding) while preserving its underlying structure, making patterns visible and interpretable.

- Linear dimensionality reduction (e.g., PCA, tPCA) assumes that the underlying structure of the data is flat. PCA, for example, captures the absolute highest amount of variance in the high dimensional data. Linear dimensionality reduction focuses on rotating, centering, and projecting data points directly onto a low-dimensional coordinate frame using linear transformations (such as matrix multiplication or orthogonal rotation). It is good for knowing where most of the variance goes and also for distances between datapoints --> to have a global representation, But bad with curved underlying structures.  
- Non linear dimensionality reduction (e.g., SNE, tSNE) assumes that the underlying structure is curved. Better adapts to local curvature of the data by calculating neighborhood similarities or proximity graphs for each point. But distances between separate clusters in a non-linear projection are frequently arbitrary, you cannot reliably infer global patterns.
 
PCA just takes the first two eigenvectors (the two directions in which the data points vary the most)  centers the data but retains the original variance scaling of each feature. If one feature tend to have much larger absolute numeric range than the others, it will dominate the covariance matrix and bias the principal components. t-PCA standardizes the variance profile across embedded coordinates. 
 
SNE maps neighborhood structures by converting high-dimensional Euclidean distances into conditional probabilities that reflect local similarities.  
