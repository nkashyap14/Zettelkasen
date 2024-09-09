# LinearRegression Sklearn

```
from sklearn import linear_model
reg = linear_model.LinearRegression()
reg.fit(data_features, data_labels) #this makes the model ready to use

label_predictions = reg.fit(new_data_features)
print('{}\n'.format(repr(label_predictions)))

print('Coefficients: {}\n'.format(repr(reg.coef_))) #prints the coefficients
print('Intercept: {}\n'.format(repr(reg.intercept_))) #prints the intercept
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
