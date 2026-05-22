# 5_4_3 Example Variance of Sample Mean Estimator Bernoulli


### Problem Statement

- Consider a set of examples 
$$
\{x_1, \dots,x_n\}
$$

- These examples are [[iid]]
	- [[Independence|independent]] and identically distributed according to a [[bernoulli distribution]] with mean theta

$$
P(x^{(i)}; \theta) = \theta^{x^{(i)}} * (1 - \theta)^{(1 - x^{(i)})}
$$

- Once again we are using the sample mean estimator which we proved was unbiased in [[5_4_2 Example Bernoulli Distribution Estimator Bias]]

$$
\hat{\theta}_m = \frac{1}{m}\sum_{i = 1}^m x^{(i)}
$$

- Now we want the variance of the estimator
$$
Var(\hat{\theta}_m) = Var(\frac{1}{m}\sum_{i = 1}^m x^{(i)})
$$

- Once again by using the properties of [[Variance]] we can pull out the constant. Then we plug in the formula for variance for a bernoulli variable for a single instance
$$
Var(\hat{\theta}_m) = \frac{1}{m^2} \sum_{i = 1}^m x^{(i)} = \frac{1}{m^2}\sum_{i = 1}^m \theta(1 - \theta) = \frac{1}{m^2}m\theta(1 - \theta) = \frac{1}{m}\theta(1 - \theta)
$$

	- So basically what this tells us is that the variance of the sample mean estimator for the bernoulli random variable is inversely proportional with m the number of examples in the dataset. Aka as the number of examples in the sampel set increases our estimator tends to have lower dispersion from the mean! Fascinating
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

