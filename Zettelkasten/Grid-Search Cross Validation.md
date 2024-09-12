# Grid-Search Cross Validation

- Technique used to obtain the best hyperparameters of a model
- Good when the dataset is small as it is an exhaustive grid search where every possible value is specified and then object goes through each possible combination and returns the model with the best combination of hyperparameters
```
from sklearn import model_selection.GridSearchCV
reg = linear_model.BayesianRidge()
params = {
  'alpha_1':[0.1,0.2,0.3],
  'alpha_2':[0.1,0.2,0.3]
}
reg_cv = GridSearchCV(reg, params, cv=5) #cv represents number of k folds
# predefined train and test sets
reg_cv.fit(train_data, train_labels)
print(reg_cv.best_params_)
```


---
Links :: [[#Example Code]] [[Computer Science]] [[sklearn]] [[K-Fold CV]] [[cross validation]]
Reference ::
Type :: #code
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2024-09-10 19:45
