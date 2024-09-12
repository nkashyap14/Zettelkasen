# K-Means Clustering sklearn

```
from sklearn.cluster import KMeans

kmeans = KMeans(n_clusters=3)

#predefined data
kmeans.fit(data)

# cluster assignments
print('{}\n'.format(repr(kmeans.labels_)))

# centroids
print('{}\n'.format(repr(kmeans.cluster_centers_)))

new_obs = np.array([
  [5.1, 3.2, 1.7, 1.9],
  [6.9, 3.2, 5.3, 2.2]])
# predict clusters
print('{}\n'.format(repr(kmeans.predict(new_obs))))
```

- KMeans object uses [[K-means++ algorithm]] to initialize [[centroids]] by default
---
Links :: [[#Example Code]] [[Computer Science]] [[sklearn]] [[Machine Learning]]
Reference ::
Type :: #code
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2024-09-12 11:37
