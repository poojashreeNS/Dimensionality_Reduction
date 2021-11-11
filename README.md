# Dimensionality_Reduction

## PCA
Principal Component Analysis is an unsupervised method that performs linear transformation to reduce the dimension of our data. It reduces the data to a lower dimension while keeping the information in our data.
PCA tries to preserve the Global Structure of data i.e when converting d-dimensional data to d’-dimensional data then it tries to map all the clusters as a whole due to which local structures might get lost.

[**Result**] PCA is mainly used for dimensionality reduction, not for visualization. There is a lot of overlapping among classes means PCA not very good for the high dimensional dataset. Very few classes can be separated but most of them are mixed.

## SVD
PCA and truncate SVD do not differ much, since they are based on the same theory that the eigenvectors with the less eigenvalue are discarded. but differs in that it works on sample matrices directly instead of their covariance matrices.

[**Result**] SVD doesn't work very well in classification when compared to PCA. It works well in noise reduction and image compression.

## LLE
LLE can be thought of as performing a PCA on each of these neighborhoods locally, producing a linear hyperplane, then comparing the results globally to find the best nonlinear embedding.
The goal of LLE is to unpack in distorted fashion the structure of the data, so often LLE will tend to have a high density in the center with extending rays.

[**Result**] LLE’s performance on the MNIST dataset is relatively poor. This is likely because the MNIST dataset consists of multiple manifolds, whereas LLE is designed to work on simpler datasets
This makes sense; its ‘represent one function as several small linear ones’ strategy likely does not work well with large and complex dataset structures.

## t-SNE
T-SNE attempts to find the underlying structure of the data by taking into account the neighbors of a sample.
T-SNE is non-linear dimensionality reduction technique.
Unlike PCA it tries to preserve the Local structure(cluster) of data by minimizing the divergence between the two distributions with respect to the locations of the points in the map.
Visualization clearly shows that T-SNE is better than PCA.
It can handle outlier.

[**Result**] t-SNE is very powerful because of this clustering vs. unrolling approach to manifold learning. With a high-dimensional and multiple-manifold dataset like MNIST, where rotations and shifts cause nonlinear relationships.

## ISOMAP
Isomap seeks a lower-dimensional representation that maintains ‘geodesic distances’ between the points. A geodesic distance is a generalization of distance for curved surfaces.
It works better than PCA as we can visualize the proper section in Isomap compared to PCA

[**Result**] Visualize the proper sectioning off digits when compared to PCA. The proximity and distance between certain groups of digits is revealing to the structure of the data. For instance, the ‘5’ and the ‘3’ that are close to each other (in the bottom left) in distance indeed look similar.

## UMAP
Uniform Manifold Approximation and Projection (UMAP) is a dimension reduction technique that can be used for visualisation similarly to t-SNE, but also for general non-linear dimension reduction.

[**Result**] UMap is great alternative for t-SNE and also consumes less time for computation. UMAP often performs better at preserving some aspects of global structure of the data than most implementations of t-SNE which is well visualized in the output.
