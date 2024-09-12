# DBSCAN

## Definition:

- Similar to [[Mean Shift Clustering]] also automatically chooses the number of clusters
- Clusters data by finding dense regions in the dataset
- Regions in the dataset with many closely packed [[data observation]] are considered high-density regions
	- Sparse data = low-density region
- Low-density regions are treated as noise and not placed in a cluster
- High-density regions are treated as clusters
	- Are defined by [[core samples]]
	- Each cluster consists of several core samples and all the observations that are neighbors to a core sample
- Highly [[Scalability|scalable]] algorithm
- Makes no assumptions about the underlying shape of clusters in the dataset

- Hyperparameters:
$$
\epsilon
$$
	- The maximum distance between two data observations that are considered neighbors
	- Smaller values of epsilon result in smaller and more tightly packed clusters
$$
minsamples
$$
	- min_samples
	- represents the minimum number of points in the neighborhood of a data observation for the observation to be considered a core sample
- [[DBSCAN sklearn]]
---
Links ::  [[Computer Science]] [[Clustering]] [[Machine Learning]]
Reference ::  [[Educative]]
Type :: #definition
Discussion ::
Date :: 2024-09-12 12:05