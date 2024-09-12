# Cross Validation sklearn

```
from sklearn import linear_model
from sklearn.model_selection import cross_val_score

clf = linear_model.LogisticRegression(max_iter=3000)

cv_score = cross_val_score(clf, data, labels, cv=3) #k folds = 3

print('{}\n'.format(repr(cv_score)))
```

- Defaults to [[R^2]] as evaluation metric  
- No need to call fit on the model prior to using the cross_val_score method as the method calls fit on the model for training each round
- For [[classification models]] applies a special form of the [[K-Fold CV]] algorithm called [[stratified K-Fold]] which means each fold will contain approximately the same class distribution as the original dataset
	- ie if original has 60% class 0 40% class 1 each fold will have same split between those observation types
---
Links :: [[#Example Code]] [[Computer Science]] [[sklearn]]
Reference ::
Type :: #code
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2024-09-09 20:06
