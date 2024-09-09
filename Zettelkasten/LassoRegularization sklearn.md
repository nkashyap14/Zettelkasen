# LassoRegularization Sklearn

```
from sklearn import linear_model
reg = linear_model.Lasso(alpha=0.1)
reg.fit(data_features, data_labels) #this makes the model ready to use


print('Coefficients: {}\n'.format(repr(reg.coef_))) #prints the coefficients
print('Intercept: {}\n'.format(repr(reg.intercept_))) #prints the intercept
print('R2: {}\n'.format(reg.score(data, labels))) #prints the r2 score from -infinity to 1
```
- There is a LassoCV object that can be used to pick the optimal alpha value
	- Reference [[RidgeRegression sklearn]] to see how to use it as the process is similar
---
Links :: [[#Example Code]] [[Machine Learning]] [[scikit-learn]] [[Computer Science]] [[cross validation]]
Reference ::
Type :: #code
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2024-09-08 17:19
