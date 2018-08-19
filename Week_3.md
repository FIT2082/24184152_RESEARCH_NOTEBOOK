# Week 3

This week was mainly focused on getting a better understanding of the dimensionality reduction algorithms, and trying to get Microscopium
up and running on our personal devices.

## PCA
Principal Component Analysis is a linear dimensionality reduction algorithm. This means it looks at scatters in N-dimensional space, and tries
to find axes in the space along which the variance of all the datapoints is maximised. In doing so, it identifies a linear combination of the features
which have the biggest effect on the overall variation of the dataset. This can be fantastic for smaller dimensions where the data is likely
to be linearly combined anyway.
However, PCA naturally does not detect any non-linear relationships in the data. Similar to applying Pearson's r to a quadratic, PCA can lead
to poor results when the data is twisted or clustered in bizarre shapes over many dimensions. Currently Microscopium uses PCA because it is
a simple implementation and has seemed promising. However, we have no reason to believe the sample space is accurately represented by a linear
combination of features. In fact, for such a large number of dimensions this is unlikely to be the case.

## t-SNE
t-Distributed Stochastic Neighbour Embedding abandons the assumption of linearity made by PCA, and is the leading standard for high dimension
reduction and visualisation. It is designed to embed high-dimensional data into a 2D or 3D space such that similar data is distributed nearby
and dissimilar data is distributed further away with high probability. Since t-SNE looks at the entire state of the local neighbourhood
by constructing a probability distribution of high dimensional point pairs and then defining a similar distribution over the low dimensional
space to minimise divergence between the two, it is likely to capture the more complex interrelationships which PCA would obscure. t-SNE also
scales reasonably to large datasets, and provided promising results in the initial exploration on the BBBC021 dataset.

## UMAP
Uniform Manifold Approximation and Projection for Dimensionality Reduction is the latest high dimension reduction algorithm proposed, and is
hailed as equivalent to t-SNE (or better) in terms of preserving global structure over the low dimensional space. It is also highly scalable
to real world datasets, and does not place a restriction on the number of dimensions. It also boasts superior run time performance to t-SNE.

## Microscopium Up & Running
We have managed to get the Bokeh app running on a test set of data, and we have discovered the command line interface used to process the images
before the embedding algorithm is run. It was suggested at the meeting that it would be easier to write a Python script which handles the pre-processing
of the files. This will be the task leading into Week 5, as we focus on drafting the Project Specification in Week 4. 
