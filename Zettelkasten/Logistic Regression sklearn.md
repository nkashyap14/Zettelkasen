# Logistic Regression Sklearn

- Default [[binary classification]]
```
from sklearn import linear_model

reg = linear_model.LogisticRegression() #default setting is binary classification
reg.fit(data, labels)

new_data = np.array([
  [  0.3,  0.5, -1.2,  1.4],
  [ -1.3,  1.8, -0.6, -8.2]])
print('Prediction classes: {}\n'.format(
  repr(reg.predict(new_data))))
```

- In order to do [[multiclass classification]]
```
from sklearn import linear_model

reg = linear_model.LogisticRegression(
solver='lbfgs',
multi_class='multinomial', max_iter=200) #default value is 'ovr'
)
reg.fit(data, labels)

new_data = np.array([
  [ 1.8, -0.5, 6.2, 1.4],
  [ 3.3,  0.8, 0.1, 2.5]])
print('Prediction classes: {}\n'.format(
  repr(reg.predict(new_data))))
```
- Have to specify multinomial otherwise it defualts to a [[One-vs-Rest classification strategy]]
	- Where one class is designated positive and all other as negative
- Uses a [[solver (sklearn)]] to obtain the optimal weight settings based on input datas and labels
	- Defaults to lbfgs
- By default logistic regression is regularized through the [[L2 Regularization (Ridge)|l2 norm of weights]]
- Like [[Ridge Regression]] and [[L1 Regularization (Lasso)]] there is also a [[cross validation|cross validated version]] of Logistic Regression in sklearn called LogisticRegressionCV
```
from sklearn import linear_model
reg = linear_model.LogisticRegressionCV(
solver='multinomial', max_iter=1000
)
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