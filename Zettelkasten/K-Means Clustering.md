# K-Means Clustering

## Definition:

- Makes the assumption that the dataset consists of spherical clusters
	- Creates clusters of observations that are circular around the centroids
	- Real life data can often not contain spherical clusters which can result in K-Means clustering producing inaccurate clusters due to this assumption
	- Alternative method is [[Hierarchical Clustering]]
- Most well known [[Clustering]] method
- Separates the data into K [[clusters]] using cluster means known as [[centroids]]
- Is an [[iterative algorithm]]
- Each iteration the algorithm assigns each [[data observation]] to the cluster with the closest centroid to the observation
- Then it updates each centroid to be equal to the new average of the data observations in the cluster
- At the beginning of the algorithm either the cluster centroids are randomly initialized
	- Can also be initialized with the [[K-means++ algorithm]]
- Clustering process stops when there are no more changes in cluster assignment for any data observation
- [[K-Means Clustering sklearn]]
- [[Mini-Batch K-Means Clustering]]
---
Links ::  [[Computer Science]]  [[Machine Learning]]
Reference ::  [[Educative]]
Type :: #definition
Discussion ::
Date :: 2024-09-12 11:34