# DBSCAN sklearn

```
from sklearn.cluster import DBSCAN

dbscan = DBSCAN(eps=1.2, min_samples=30)

dbscan.fit(data)

# cluster assignments
print('{}\n'.format(repr(dbscan.labels_)))

# core samples
print('{}\n'.format(repr(dbscan.core_sample_indices_)))
num_core_samples = len(dbscan.core_sample_indices_)
print('Num core samples: {}\n'.format(num_core_samples))
```


---
Links :: [[#Example Code]] [[Computer Science]] [[sklearn]]
Reference ::
Type :: #code
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2024-09-12 12:12
