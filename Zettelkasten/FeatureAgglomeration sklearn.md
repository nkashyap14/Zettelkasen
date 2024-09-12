# FeatureAgglomeration sklearn

```
from sklearn.cluster import FeatureAgglomeration

agg = FeatureAgglomeration(n_clusters=2)
new_data = agg.fit_transform(data)
print('New shape: {}\n'.format(new_data.shape))
print('First 10:\n{}\n'.format(repr(new_data[:10])))
```

- n_clusters specifies new feature dimensions of the data
---
Links :: [[#Example Code]] [[Computer Science]] [[sklearn]] [[Clustering]] [[Machine Learning]]
Reference ::
Type :: #code
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2024-09-12 12:21
