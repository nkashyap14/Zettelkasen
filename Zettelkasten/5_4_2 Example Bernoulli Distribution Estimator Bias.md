# 5_4_2 Example Bernoulli Distribution Estimator Bias

- Let us determine the [[bias]] of an estimator for a [[Bernoulli Distribution]]
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

- A common estimator for the theta parameter is the [[mean]] of the training samples

$$
\hat{\theta}_m = \frac{1}{m}\sum_{i = 1}^m x^{(i)}
$$

	- m is the number of training samples

- To determine whether the estimator is biased we substitute the estimator into the following equation which is the equation for the bias of an estimator. Remember an [[unbiased estimator]] is one where it's bias is equal to 0  meaning that its expected value is the parameter it is trying to estimate

$$
bias(\hat{\theta_m}) = \mathbb{E}(\hat{\theta_m}) - \theta
$$

- So math flows as
$$
bias(\hat{\theta_m})  = \mathbb{E}[\frac{1}{m}\sum_{i = 1}^m x^{(i)}] - \theta 
$$

	- With the [[linearity property of expectations]] we pull out the constant and the summation

$$
bias(\hat{\theta_m})  = \frac{1}{m}\sum_{i = 1}^m \mathbb{E}[x^{(i)}] - \theta 

$$

	- Then we can plug in the formula for [[expected value]] which is a summation over all the values times their probabilities
$$
bias(\hat{\theta_m})  = \frac{1}{m}\sum_{i = 1}^m \sum_{x^{(i) = 0}}^1[x^{(i)} *\theta^{x^{(i)}}(1 - \theta)^{(1 - x^{(i)})}] - \theta 
$$

		- Reason it becomes like this is remember a [[Bernoulli Random Variable]] only takes on values 1 or 0
			- That is why we have a summation over 0 and 1
		- Furthermore we just are multiplying the input by the probability distribution for the [[Bernoulli Random Variable]] defined above!
- This then becomes

$$
bias(\hat{\theta_m})  = \frac{1}{m}\sum_{i = 1}^m(\theta) - \theta
$$

		- The reason the value in the inner brackets simplifies to one is that when the input takes on the value 0 the sum becomes equal to (1 - theta) and when it is equal to 1 the inner value becomes theta. Both those values are of course multiplied by their input value as well due to the expected value form. So the summation is 0(1 - theta) + 1(theta) which becomes theta! So the sample mean of the bernoulli random variable is theta itself the probability the variable takes on the value 1.

	- Which finally becomes
$$
bias(\hat{\theta}_m) = \theta - \theta = 0
$$

- And thusly we have proved that the sample mean as an estimator for the theta parameter of a bernoulli random distribution, aka the probability of the random variable taking on the value 1, is an unbiased estimator aka that its expected value is equal to the underlying parameter and that over the long run with enough samples it will converge to that value! Fascinating result

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

