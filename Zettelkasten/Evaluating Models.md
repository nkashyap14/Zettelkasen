# Evaluating Models

## Details:

- For [[Regression]] models we normally use [[Mean Squared Error (MSE)]], [[Mean Absolute Error (MAE)]], or [[R^2]]
	- Most common is MAE as it represents the natural definition of error
	- Use MSE when we want to penalize really bad predictions as the errors get squared
- For classification models use the accuracy on the test set as the evaluation metric
- Example code below for regression metrics
```
reg = tree.DecisionTreeRegressor()
# predefined train and test sets
reg.fit(train_data, train_labels)
predictions = reg.predict(test_data)

from sklearn import metrics
r2 = metrics.r2_score(test_labels, predictions)
print('R2: {}\n'.format(r2))
mse = metrics.mean_squared_error(
  test_labels, predictions)
print('MSE: {}\n'.format(mse))
mae = metrics.mean_absolute_error(
  test_labels, predictions)
print('MAE: {}\n'.format(mae))
```

- Example code below for classification metrics
```
# predefined train and test sets
clf.fit(train_data, train_labels)
predictions = clf.predict(test_data)

from sklearn import metrics
acc = metrics.accuracy_score(test_labels, predictions)
print('Accuracy: {}\n'.format(acc))
```
---
Links ::  [[Computer Science]] [[Machine Learning]] [[sklearn]]
Reference ::  [[Educative]]
Type :: #definition
Discussion ::
Date :: 2024-09-10 19:42