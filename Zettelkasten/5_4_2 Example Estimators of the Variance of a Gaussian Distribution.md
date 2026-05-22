# 5_4_2 Example Estimators of the Variance of a Gaussian Distribution

- Let us determine the [[bias]] of a variance estimator for a [[Gaussian Distribution]]
- Let us first see if the sample variance is an unbiased estimator
- Let us understand what is an unbiased estimator for population variance
### Problem Statement

- First estimator we consider is sample variance
$$
\hat{\sigma^2_m} = \frac{1}{m}\sum_{i=1}^m (x^{(i)} - \hat{\mu}_m)^2
$$

	-  mu_m is the sample mean


- We must compute the bias
$$
bias(\hat{\sigma^2_m})  = \mathbb{E}[\hat{\sigma^2_m}] - \sigma^2
$$

- First we can evaluate the expectation term to make our math a bit easier

$$
\mathbb{E}[\hat{\sigma^2_m}] = \mathbb{E}{[\frac{1}{m}\sum_{i=1}^m (x^{(i)} - \hat{\mu}_m)^2]}
$$
- First we must expand the squared term

$$
(x^{(i)} - \hat{\mu}_m)^2 = [(x^{(i)} - \mu) - (\mu_m - \mu)]^2 = (x^{(i)} - \mu)^2 - 2(x^{(i)} - \mu)(\hat{\mu}_m - \mu) + (\hat{\mu}_m - \mu)^2
$$
		- We can do this expansion because if you lok at the term we have just added population mean and subtracted population mean (mu). This is equivalent to adding 0 to the term so the overall term is the same.
		- Then we expanded the square
- Now we must sum over all samples 
	- Notice we apply the summation only on the terms that depend on x_i

$$
\sum_{i=1}^m (x^{(i)} - \hat{\mu}_m)^2 = \sum_{i=1}^m(x^{(i)} - \mu)^2 - 2(\hat{\mu}_m - \mu) \sum_{i=1}^m(x^{(i)} - \mu) + \sum_{i=1}^m(\hat{\mu}_m - \mu)^2
$$

	- We can simplify the middle term:
$$
\sum_{i=1}^m(x^{(i)} - \mu) = \sum_{i=1}^mx^{(i)} - m\mu = m\hat{\mu_m} - m\mu = m(\hat{\mu_m} - \mu)
$$

		- The reason the first summation becomes m * sample mean is due to the definition of the sample mean estimator
		- Refer to [[5_4_2 Example Gaussian Distribution Estimator of the Mean]] for more info
	- Similarly third term just becomes m times the quantity squared as we summate the term m times
- Equation becomes
$$
\sum_{i=1}^m(x^{(i)} - \mu)^2 - 2m(\hat{\mu}_m - \mu)^2 + m(\hat{\mu_m} - \mu)^2 
$$
		- This stems from the fact that we are multiplying the term we simplified by what was already calculated in the middle term
		- Then we notice we can add the 2nd and third term to simplify even more to
$$
\sum_{i=1}^m(x^{(i)} - \mu)^2 - m(\hat{\mu}_m - \mu)^2
$$

	-  So we have simplified the term inside the expectation as muh as we could. Now we must take the expectations
	- We can also separately take expectation due to the property of [[linearity of expectations]]
$$
= \frac{1}{m}[\mathbb{E}[\sum_{i=1}^m(x^{(i)} - \mu)^2] - \mathbb{E}[m(\hat{\mu}_m - \mu)^2]]
$$

		- We can temporarily ignore the 1/m and focus on evaluating each expectation term

$$
\mathbb{E}[\sum_{i=1}^m(x^{(i)} - \mu)^2] = m\sigma^2
$$
	- The reason is [[Variance|Formula for Variance]]
		- Variance is just the expectation of the squared deviation from population mean
		- We pull the summation out as well
	- Now for the second term
$$
\mathbb{E}[m(\hat{\mu}_m - \mu)^2]] = Var(\hat{\mu_m}) = Var(\frac{1}{m}\sum_{i = 1}^m x^{(i)}) = \frac{1}{m^2}Var(\sum_{i = 1}^m x^{(i)}) = \frac{1}{m^2}m\sigma^2 = \frac{\sigma^2}{m}
$$

		- We made the 1/m into 1/m^2 by the [[Variance|Properties of variance]] specifically the property about variance times a constant.
- Now that we have the two expectation terms solved we can plug the values in
$$
= [\mathbb{E}[\sum_{i=1}^m(x^{(i)} - \mu)^2] - \mathbb{E}[m(\hat{\mu}_m - \mu)^2]] = m\sigma^2 - m\frac{\sigma^2}{m} = m\sigma^2 - m = (m - 1)\sigma^2
$$

- Lastly we had the 1/m outside the term we left out to simplify the algebra. Now we multiply by that to get our final value as

$$
\mathbb{E}[\hat{\sigma^2_m}] = \frac{1}{m} *(m-1)\sigma^2 = \frac{(m - 1)}{m}\sigma^2
$$

- So we got the expectation of our sample variance. Now we wanted to calculate the bias so we must subtract that by sigma^2.
$$
bias(\hat{\sigma^2_m}) = \frac{(m - 1)}{m}\sigma^2 - \sigma^2 = \frac{-\sigma^2}{m}
$$

- This lets us conclude that the sample variance is a biased estimator for population variance. Fascinating thing we have just proved!
- The actual unbiased estimator for sample variance is 
$$
\tilde{\sigma_m}^2 = \frac{1}{m - 1}\sum_{i=1}^m (x^{(i)} - \hat{\mu_m})^2
$$

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

