# L2 Regularization (Ridge)

## Definition:

- Find weights that minimize the quantity
$$
\alpha||w||^2_2 + \sum^n_{i=1}{(x_i*w - y_i)^2}
$$

$$
\alpha = non-negative - hyperparameter
$$
$$
||w||^2_2 = L2-norm-of-weights
$$

- Two terms above act as a penalty term as they penalize larger weight values
- Larger values of alpha put greater emphasis on the penalty term forcing the model to have even smaller weight values
---
Links ::  [[Computer Science]] 
Reference ::  [[Educative]] [[Data Modeling with scikit-learn]]
Type :: #definition
Discussion ::
Date :: 2024-09-08 17:32