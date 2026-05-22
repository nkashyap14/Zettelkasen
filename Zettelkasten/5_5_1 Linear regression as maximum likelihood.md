# 5_5 General Setup Maximum Likelihood


### Problem Statement

- First let us set the context. In [[5_1_4 Example Linear Regression]] we walked through linear regression with [[Mean Squared Error (MSE)]] as the optimization criterion. We showed how there is a closed form solution to minimizing that.
- Now let us show how that procedure may also be justified as a maximum likelihood procedure
- Because we are viewing this from the perspective of maximum likelihood estimation we can now view linear regression as rather than producing a single prediction y_hat, think of it as producing a probability distribution conditioned on x
$$
p(y | x)
$$
	- Basically we might have several training examples with the same input value but different values of y over an infinitely large training set so we model it like this
	- Goal then becomes to fit the  distribution to all those different y values that are compatible with x
- We must define the conditional distribution of model. To connect to the previous algorithm we will define our conditional as a gaussian. 
$$
p(y | x) = \mathcal{N}(y;\hat{y}(x;w), \sigma^2)
$$
	- In this we are assuming variance is set to some constant chosen by the user
	- The function y_hat aims to predict the meanof the gaussian
- Since we assume examples are [[i.i.d]] the conditional log likelihood equation to maximize is 
$$
\sum_{i=1}^m log[p(y^{(i)}|x^{(i)};\theta]
$$
	- First we start by plugging in the gaussian formula as we defined above
		- As we can see in the formula above y is the sample from our empirical distribution we pass into the model. y_hat is our predicted mean
$$
\sum_{i=1}^m log[\frac{1}{\sqrt{2\pi\sigma^2}}exp(-\frac{(y^{(i)} - \hat{y}(x;\theta))^2}{2\sigma^2})]
$$
	- For convenience sake let us drop the conditioning on x_i and theta
	- Then we use the [[properties of logarithms]] to change the gaussian formula into 
$$
log[\frac{1}{\sqrt{2\pi\sigma^2}}] + log(exp(-\frac{(y^{(i)} - \hat{y})^2}{2\sigma^2}))
$$
	- We can further simplify by realizing two pi sigma squared is raised to the negative one half. Also considering we take the natural log we can drop the exp due to the definition of a logarithm
$$
-\frac{1}{2}log[2\pi\sigma^2]  -\frac{(y^{(i)} - \hat{y})^2}{2\sigma^2}
$$
	- This equation is our log likelihood for a single datapoint. We can plug this into our summation
$$
\sum_{i=1}^m-\frac{1}{2}log[2\pi\sigma^2]  -\frac{(y^{(i)} - \hat{y})^2}{2\sigma^2})
$$

		- We can distribute the summation over the two terms annd pull out constants

$$
-\frac{1}{2}\sum_{i=1}^m log[2\pi\sigma^2]  - \sum_{i=1}^m\frac{(y^{(i)} - \hat{y})^2}{2\sigma^2})
$$
		- Then from there we can pull out the sigma^2 from the second as it is a constant chosen by the user. We also drop the summaton and multiply by m as we summate the first term m times.
$$
-\frac{m}{2} log[2\pi\sigma^2]  - \frac{1}{2\sigma^2}\sum_{i=1}^m(y^{(i)} - \hat{y})^2)
$$
		- Thusly this is the final form of our conditional log likelihood equation for the linear regression model when we assume our models distribution to be gaussian. 
		- Now remember we are maximizing over theta and assuming a fixed variance. This means the first term is a constant. This means maximizing the log likelihood depends on the second term
		- Maximizing a negative of a sum is equivalent to minimizing the sum itself
$$
\operatorname*{argmax}_{\theta} - sum = \operatorname*{argmin}_{\theta}sum
$$
		- This is because the lower we make the sum the closer it is to 0 from the negative side of the number scale which makes it a larger negative number
		- Once again we can drop the constant being multiplied. Maximizing the log likelihood is equivalent to maximizing that term.
	- Remember the formula for [[Mean Squared Error (MSE)]]
$$
MSE_{test} = \frac{1}{m}\sum_i (\hat{y}^{(test)} - y^{(test)})^2_i
$$
		- As we can see the second term above is the negative of the second term above. Because we seem to argmax the log likelihood sum and in reality it just depends on the second term we can see that argmaxing the log likelihood, assuming some fixed variance, is in reality equal to minimizing our mean squared error!
	- Thusly what we have concluded is that under the assumption that we are dealing with an empirical distribution that is drawn from a true data generating process with a  conditional distribution, maximizing the log likelihood of the samples of the empirical distribution amounts based on our linear regression model that outputs a gaussian mean minimizing the mean squared error is equivalent to maximizing the log likelihood.
	- This is why MSE is the optimal loss function for linear regression when assuming a Gaussian distribution for our underlying ground truth


---
Topics ::  [[Deep Learning]] [[linear regression]] [[]]
Reference ::
Type :: #molecule
Creator ::
Rating ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2025-10-01 20:36

