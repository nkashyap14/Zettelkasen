# Decision Tree sklearn

```
from sklearn import tree

clf_tree1 = tree.DecisionTreeClassifier()
reg_tree1 = tree.DecisionTreeRegressor()
clf_tree2 = tree.DecisionTreeClassifier(
max_depth=8
)
reg_tree2 = tree.DecisionTreeRegressor(
max_depth=5
)

# predefined dataset
print('Data shape: {}\n'.format(data.shape))
# Binary labels
print('Labels:\n{}\n'.format(repr(labels)))
clf_tree1.fit(data, labels)
```

- max_depth allows us to manually set the maximum number of layers allowed in the decision tree
	- Defaults to none which means the decision tree continues to be constructed until no nodes can have anymore children

---
Links :: [[#Example Code]] [[Computer Science]] [[sklearn]]
Reference ::
Type :: #code
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2024-09-09 19:46
