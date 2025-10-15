hic# 5_1_4 Example Linear Regression

- Linear regression is the simplest machine learning algorithm
- Used to solve a regression problem
- Takes below x as vector input and predicts a scalar y
- $$x \in\mathbb{R}^n, y\in \mathbb{R}$$ 
- y hat is the value our model predicts. Defined to be. w transpose is a vector of parameters

$$
\hat{y} = w^Tx, w\in \mathbb{R}^n
$$

- Think of w as a set of weights that defines how each feature affects the prediction. Positive weight = increasing feature increases the value of our prediction. Negative weight = increasing feature decreases value of our prediction

- Measure performance of linear regression models via [[Mean Squared Error (MSE)]]
$$
MSE_{test} = \frac{1}{m}\sum_i (\hat{y}^{(test)} - y^{(test)})^2_i
$$
	- So basically total mean squared error is the average of our squared deviations of our estimated value from the value we were aiming to predict
	$$
	MSE_{test} =\frac{1}{m}||\hat{y}^{(train)} - y^{(train)}||^2_2
	$$
	- It is equivalent to the squared Euclidean  distance between the prediction vectors and the target vectors divided by the number of errors. That is why whenever Euclidean distance between our predictions and our targets increase our error increases

- Aim to minimize the MSE
	- So can solve for where its gradient is equal to 0 as that is the minima

$$
\nabla_w MSE_{train} = 0 \rightarrow \nabla_w\frac{1}{m}||\hat{y}^{(train)} - y^{(train)}||^2_2 = 0
$$

		- Above says take the derivative of MSE train with respect to 0 and set it equal to 0. We then plug in the formula for MSE train which  is the euclidean formula
- Next we can transform the equation on the right side. First we will plug in the values for y_hat train which is just the feature set times our weight vector. And we can also pull out the 1/m from the quantity and move it to the left of the derivative. The reason is that it is a constant value that isn't dependent on the parameter we are taking the derivative with respect to.
- Still solving with respect to 0

$$
\frac{1}{m}\nabla_w||X^{(train)}w - y^{(train)}
||^2_2 = 0$$

	- Next what we can do is apply the formula for squared l2 norm of a vector. Basically we treat the inside quantity as a vector (difference of two vectors is still a vector). 
	- A general property is that the squared Euclidean norm of a vector is just the dot product of the vector transpose with the vector.
	- Then the equation becomes

$$
\nabla_w(X^{(train)}w - y^{(train)})^T(X^{(train)}w - y^{(train)}) = 0
$$

	- Now we do distributive multiplication with [[FOIL]] (First term multiplication, Outer Term Multiplication, Inner Term Multiplication, Last Term multiplication)

$$
\nabla_w(w^TX^{(train)T}X^{(train)}w - w^TX^{(train)T}y^{(train)} - y^{(train)T}X^{(train)}w + y^{(train)T}y^{(train)}) = 0
$$
		- So the inner eleements can be added because of a few properties
		- One remember a transpose of a scalar is a scalar
		- Now let us remember dimensions. 
			- y_train is: m x 1
				- M samples each of which has a single scalar value we aim to predict
			- Xtrain is : m x n:
				- M samples
				- N features
			- w is : n x 1: 
				- column vector
				- n features each of which has a weight as their own row
				- When we predict x train is multipliedinto thi
			- w transpose is : 1 x n
				- Row vector
			- y transpose is: 1 x m
				- Row vector
			- Xtrain transpose is  n x m
	- So let us trace out the dimensions of these multiplciations
		- w_transpose x X_train transpose x y train:
			- (1 x n) times (n x m) times (m x 1)
			- As we remember m x n times n x p gives output m x p
			- so this becomes (1 x n) times (n x 1)
			- and finally it becomes (1 x 1) A scalar
		- y_train transpose x X_train x w 
			- (1 x m) times (m x n) times (n  x 1) 
			- Becomes (1 x m) times (m x 1)
			- Becomes (1 x 1) A scalar again
		- Also those two terms are equal because if you take the transpose of 1 it becomces the other 
			- As you can see below when you take a transpose of ABC you reverse the order of the multiplication and then apply transpose operation. 

$$
(w^TX^{(train)T}y^{(train)})^T
 = y^{(train)T}X^{(train)}w$$
			- As such these two terms are equal and we can add them together as we do any algebraic quantity. Thusly the original function simplifies to
$$
\nabla_w(w^TX^{(train)T}X^{(train)}w - 2w^TX^{(train)T}y^{(train)}  + y^{(train)T}y^{(train)}) = 0
$$

- Now we apply the gradient aka take the derivative with respect to w of all its parameters
	- The third term doesnt depend on w so it goes to 0
	- The second term is simple application of the derivative. It is to the first degree so everything it is multiplied becomes the derivative
	- The first term is basically the quadratic form of the w vector. As such we pull out a 2 keep the w when doing the derivation along with all the constants its multiiplied by
	- Thus it becomes 

$$
2X^{(train)T}X^{(train)}w - 2X^{(train)T}y^{(train)} = 0
$$
	- From there it is a simple algebraic solve for w which was our goal the entire time. Get a set of weights or w that makes our derivative = 0 which is a closed form solution for a global minima. This can be solved in this way because we are working with LINEAR transformations. Nonlinear transformations would not have worked out like this
	- Simply send the second term to the right side
	- Divide by 2
	- Take the inverse of the matrix multiplication because its not a simple division you need to invert transformations that the matrixes represent to cancel out their effect and apply it on the right side as well
	- Results in the equation
$$
w = (X^{(train)T}X^{(train)})^{-1}X^{(train)T}y^{(train)}
$$

		- So these systems of equations are called the normal equations. The solution for these give us the optimal set of weight parameters that give us a gradient = 0 for LINEAR REGRESSION
	- Another key point. The inverted term on the left you see must be full rank aka no linearly dependent columns which results in them being invertible. So the features you pass into the model must not be collinear and feature selection is important
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

