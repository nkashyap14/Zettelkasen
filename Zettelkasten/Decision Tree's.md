# Decision Tree's

## Definition:

- Popular model for both [[Classification]] and [[Regression]]
- Is a [[binary tree]] where each node of the tree decides on a particular [[feature]]
	- Descend either to left or right child depending on feature value
	- Feature can be boolean or numeric
- Leaves of the decision tree determine the class label (classification) or the real number value to predict (regression)
- Decision tree's are prone to [[overfitting]] data
- Goal is to pick features at each node that best split the remaining dataset
	- Options to decide
		- [[Gini Impurity]]
		- [[Mean Squared Error (MSE)]]
		- [[Mean Absolute Error (MAE)]]
	- For classifications tree's choose the feature at each node that minimizes the remaining dataset observations Gini Impurity
		- MAE/MSE for regression
- [[Decision Tree sklearn]]
---
Links ::  [[Computer Science]] [[Machine Learning]] [[Data Modeling with scikit-learn]]
Reference ::  [[Educative]]
Type :: #definition
Discussion ::
Date :: 2024-09-09 19:43