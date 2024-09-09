## Definition:

- Find weights that minimize the quantity
$$
\alpha||w||_1 + \sum^n_{i=1}{(x_i*w - y_i)^2}
$$

$$
\alpha = non-negative - hyperparameter
$$
$$
||w||_1 = L1-norm-of-weights
$$

- Tends to prefer linear models with fewer parameter values
- Tends to zero out some of the weight coefficients
- Reduces the number of features that the model is dependent on which can be beneficial when some features are completely irrelevant or duplicates of other features
- [[LassoRegularization sklearn]]
---
Links ::  [[Computer Science]] 
Reference ::  [[Educative]] [[Data Modeling with scikit-learn]]
Type :: #definition
Discussion ::
Date :: 2024-09-08 17:32