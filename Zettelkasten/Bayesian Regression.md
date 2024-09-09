# Bayesian Regression

## Definition:

- Offers a way to optimize the [[hyperparameter|hyperparameters]] of a [[regularization|regularized regression model]]
- Central idea is to make assumptions about the [[Cumulative Distribution Function|probability distribution]] of a model's parameters before being fitted on the data
	- Initial assumptions are called priors
- Hyperparameters optimized
	- Alpha: Same purpose as [[Ridge Regression]]
		- Scaling factor for penalty term
	- Lambda: Acts as the precision of the model's weights
		- Smaller the Lambda value the greater the variance between individual weight values
- Both hyperparameters have [[gamma distribution]] priors
	- We assume both values come from a gamma distribution
	- Gamma distribution is a probability distribution defined by a shape parameter and a scale parameter
$$
\alpha, \lambda
$$

$$
\alpha_{prior} = \Gamma(\alpha_1,\alpha_2)
$$
$$
\lambda_{prior} = \Gamma(\lambda_1, \lambda_2)
$$
- Where below is a gamma distribution with shape parameter k and scale parameter theta
$$
\Gamma(k,\theta)
$$

-  [[RidgeRegression sklearn]]
- [[BayesianRegression sklearn]]
---
Links ::  [[Computer Science]] [[Regression]] [[Bayes' Rule]]
Reference ::  [[Educative]]
Type :: #definition
Discussion ::
Date :: 2024-09-09 19:24