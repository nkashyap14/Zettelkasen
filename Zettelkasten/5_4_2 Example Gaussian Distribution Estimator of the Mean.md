# 5_4_2 Example Gaussian Distribution Estimator of the Mean

- Let us determine the [[bias]] of an estimator for a [[Gaussian Distribution]]
### Problem Statement

- Consider a set of examples 
$$
\{x_1, \dots,x_n\}
$$

- These examples are [[iid]]
	- [[Independence|independent]] and identically distributed according to a [[Gaussian Distribution]] 

$$
p(x^{(i)}; \mu,\sigma^2) = N(x^{(i)}; \mu, \sigma^2)
$$

- A common estimator for the theta parameter is the [[mean]] of the training samples

$$
\hat{\mu}_m = \frac{1}{m}\sum_{i = 1}^m x^{(i)}
$$

	- m is the number of training samples

- To determine whether the estimator is biased we substitute the estimator into the following equation which is the equation for the bias of an estimator. Remember an [[unbiased estimator]] is one where it's bias is equal to 0  meaning that its expected value is the parameter it is trying to estimate

$$
bias(\hat{\mu}) = \mathbb{E}(\hat{\mu_m}) - \mu
$$

- So math flows as
$$
bias(\hat{\mu})  = \mathbb{E}[\frac{1}{m}\sum_{i = 1}^m x^{(i)}] - \mu 
$$

	- With the [[linearity property of expectations]] we pull out the constant and the summation

$$
bias(\hat{\mu})  = \frac{1}{m}\sum_{i = 1}^m \mathbb{E}[x^{(i)}] - \mu 

$$

	- Then we can plug in the formula for [[expected value]] which is a summation over all the values times their probabilities. By the [[properties of Gaussian]] we know that the mean of the gaussian is just the mu. So we can substitute that value in
$$
bias(\hat{\mu})  = \frac{1}{m}\sum_{i = 1}^m \mu - \mu $$

- This then becomes

$$
bias(\hat{\theta_m})  = \mu - \mu = 0
$$


- And thusly we have proved that the sample mean as an estimator for the mu parameter of a Gaussian probability distribution, is an [[unbiased estimator]]

---
Topics ::  [[Deep Learning]]
Reference ::
Type :: #molecule
Creator ::
Rating ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2025-10-01 20:36

