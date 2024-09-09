# RidgeRegression Sklearn

```
from sklearn import linear_model
reg = linear_model.Ridge(alpha=0.1) #alpha is the hyperparameter that influences how much weight to put on the penalty term that reduces the size of weights. Defaults to 1.0
reg.fit(data_features, data_labels) #this makes the model ready to use

r2 = reg.score(new_data_features, new_data_labels)
print('R2: {}\n'.format(r2))
```

- Can optimally choose alpha value by using cross-validation with the RidgeCV object

```
from sklearn import linear_model
alphas = [0.1, 0.2, 0.3]
reg = linear_model.RidgeCV(alphas=alphas)
reg.fit(data_features, data_labels)
print('Coefficients: {}\n'.format(repr(reg.coef_)))
print('Intercept: {}\n'.format(reg.intercept_))
print('Chosen alpha: {}\n'.format(reg.alpha_))
```
---
Links :: [[#Example Code]] [[Machine Learning]] [[scikit-learn]] [[Computer Science]]
Reference ::
Type :: #code
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2024-09-08 17:19
