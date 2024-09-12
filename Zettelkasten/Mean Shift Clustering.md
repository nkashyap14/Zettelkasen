# Mean Shift Clustering

## Definition:

- An [[Algorithm]] that can help us pick the number of clusters for us
- Based on finding cluster [[centroids]]
- Algorithm automatically looks for blobs in the data that can be potential candidates for clusters
- Using the blobs the algorithm finds a number of candidate centroids
	- Removes candidates that are basically duplicates of others to form the final set
- The final set determines the number of clusters as well as dataset cluster assignments
	- [[data observation|data observations]] are assigned to the nearest centroid
- [[Mean Shift Clustering sklearn]]
- Issues:
	- Not very [[Scalability|scalable]] due to sheer computation time
	- Makes assumption that the clusters have a blob like shape
		- Weaker assumption than [[K-Means Clustering]] however still an assumption

---
Links ::  [[Computer Science]] [[Machine Learning]] [[Clustering]]
Reference ::  [[Educative]]
Type :: #definition
Discussion ::
Date :: 2024-09-12 11:54