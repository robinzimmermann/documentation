# ClusterCosineSimilarity

Measures the intra-cluster similarity of a clustering model using cosine similarity.

**1. Purpose:**
The purpose of this metric is to measure how similar the data points within each cluster of a clustering model are.
This is done using cosine similarity, which compares the multi-dimensional direction (but not magnitude) of data
vectors. From a Model Risk Management perspective, this metric is used to quantitatively validate that clusters
formed by a model have high intra-cluster similarity.

**2. Test Mechanism:**
This test works by first extracting the true and predicted clusters of the model's training data. Then, it computes
the centroid (average data point) of each cluster. Next, it calculates the cosine similarity between each data
point within a cluster and its respective centroid. Finally, it outputs the mean cosine similarity of each cluster,
highlighting how similar, on average, data points in a cluster are to the cluster's centroid.

**3. Signs of High Risk:**

- Low mean cosine similarity for one or more clusters: If the mean cosine similarity is low, the data points within
the respective cluster have high variance in their directions. This can be indicative of poor clustering,
suggesting that the model might not be suitably separating the data into distinct patterns.
- High disparity between mean cosine similarity values across clusters: If there's a significant difference in mean
cosine similarity across different clusters, this could indicate imbalance in how the model forms clusters.

**4. Strengths:**

- Cosine similarity operates in a multi-dimensional space, making it effective for measuring similarity in high
dimensional datasets, typical for many machine learning problems.
- It provides an agnostic view of the cluster performance by only considering the direction (and not the magnitude)
of each vector.
- This metric is not dependent on the scale of the variables, making it equally effective on different scales.

**5. Limitations:**

- Cosine similarity does not consider magnitudes (i.e. lengths) of vectors, only their direction. This means it may
overlook instances where clusters have been adequately separated in terms of magnitude.
- This method summarily assumes that centroids represent the average behavior of data points in each cluster. This
might not always be true, especially in clusters with high amounts of variance or non-spherical shapes.
- It primarily works with continuous variables and is not suitable for binary or categorical variables.
- Lastly, although rare, perfect perpendicular vectors (cosine similarity = 0) could be within the same cluster,
which may give an inaccurate representation of a 'bad' cluster due to low cosine similarity score.