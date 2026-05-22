# 5_6 Bayesian Linear Regression

- Linear regression is the simplest machine learning algorithm
- Used to solve a regression problem
- Takes below x as vector input and predicts a scalar y
- $$x \in\mathbb{R}^n, y\in \mathbb{R}$$ 
- y hat is the value our model predicts. Defined to be. w transpose is a vector of parameters

$$
\hat{y} = w^Tx, w\in \mathbb{R}^n
$$
- For this example we are given a set of m training examples (X_train, Y_train). Our prediction of y over the entire training set can be expressed as
$$
\hat{y}_{train} = X^{(train)}w
$$
- We can also express it as a gaussian conditional distribution on y_train and it becomes
$$
p(y^{(train)}|X^{(train)}, w) = \mathcal{N}(y^{(train)};X^{(train)}w, I) \propto exp(-\frac{1}{2}(y^{(train)} - X^{(train)}w)^T(y^{(train)} - X^{(train)}w))
$$
	- So it is a [[multivariate gaussian]] where the variance is defined to be the identity matrix
	- And the mean is X_train(our entire training samples batch) times w our vector of parameters
	- This funciton above is defining our likelihood
	- Remember the general formula for the pdf of a multivariate gaussian is
$$
p(x) = \frac{1}{(2\pi)^{\frac{n}{2}}|\Sigma|^\frac{1}{2}}exp(-\frac{1}{2}(x - \mu)^T\Sigma^{-1}(x-\mu))
$$
		- We have defined our variance as the identity matrix so the determinant term alongside the inverse term vanish from the quadratic form.
		  - We can think of it as being proportional to just the term in the exponent as the constants out front drop
- To reduce notational burden from now on (X, y) will denote X_train, y_train
- We seek to define a posterior distribution over the model parameter vector w
- To do so we need a prior which reflects our naive belief about the value of these parameters
	- We should assume a broad distribution that encodes a high degree of uncertainty about our parameters. For real-valued parameters it is common to use a gaussian
- Thus our prior becomes

$$
p(w) = \mathcal{N}(w;\mu_0,\Lambda_0) \propto exp(-\frac{1}{2}(w - \mu_0)^T\Lambda_0^{-1}(w-\mu_0))
$$
	- Mu_0 and Lambda_0 are the prior distribution mean vector  and covariance matrix vector
- Now that we have our prior and our likelihood we can move onto determining our posterior distribution over the model's parameters

$$
p(w | X, y) \propto p(y | X, w)p(w)
$$
	- Plug in our values we and get
$$
\propto exp(-\frac{1}{2}(w - \mu_0)^T\Lambda_0^{-1}(w-\mu_0)) * exp(-\frac{1}{2}(y - Xw)^T(y - Xw)
$$
		- I'm saving the writing down of some of the steps. For understandings sake just know the next bit is expanding and collecting terms. So you internally multiply out all the terms for both exps and then sum them together, as they are both being exponentiated by the same base, to get
$$
p(w|X, y) \propto exp(-\frac{1}{2}(-2y^TXw + w^TX^TXw = w^T\Lambda_0^{-1}w - 2\mu_0^T\Lambda_0^{-1}w))
$$
		- Now define the following vvalues for Lambda_m and mu_m
	$$
	\Lambda_m = (X^TX + \Lambda_0^{-1})^{-1}, \mu_m = \Lambda_m(X^Ty + \Lambda_0^{-1}\mu_0)
	$$
	- Then the posterior can be rewritten as a gaussian distribution in the form of 

$$
p(w|X, y) \propto exp(-\frac{1}{2}(w-\mu_m)^T\Lambda_m^{-1}(w-\mu_m))
$$


	- We can get some intuition for the effect of bayesian inference t. Most times we initialize mu_0 to 0. If we set Lambda_0 to 1/alpha * I. Then mu_m will give the same estimate of w as does frequentist linear regression with a weight decay penalty of alpha * w^T * w
		- So the optimal w that minimizes the cost function for ridge regression is the most likely w that is given by bayesian linear regression so long as you assume the same alpha as applied on ridge regression
	- Most important difference is that the bayesian estimate also comes with a covariance matrix which shows how likely different values of w are rather than only a point estimate of the mu_m parameter of the posterior.

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

