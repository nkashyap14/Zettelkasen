# train_test_split

```
from sklearn.model_selection import train_test_split

split_dataset = train_test_split(data,labels)

train_data = split_dataset[0]
test_data = split_dataset[1]
train_labels = split_dataset[2]
test_labels = split_dataset[3]
```

#### Details

- Utility function from sklearn that handles dataset splitting into [[training data]] and [[testing data]]
- Randomly shuffles the dataset and corresponding labels in order to remove any systematic ordering that could impact the model in training
- Default size of testing set is 25% of the original dataset
	- Can use test_size keyword argument to specify percentage

---
Links :: [[#Example Code]] [[API]] [[API Details]] [[sklearn]]
Reference ::
Type :: #code
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2024-09-09 19:53
