# Properties of Expectation

- X = random variable and Y = function
$$
Y = g(X)
$$
$$
\text{Hard } \mathbb{E}[Y] = \sum_{y} y \cdot P_Y(y)
$$
$$
\text{Easy } \mathbb{E}[Y] = \sum_{x} g(x) \cdot P_X(x)
$$
$$
\mathbb{E}[g(X)] \neq g(\mathbb{E}[X])
$$

	- Expectations are like averages however the average of a function is not the same as the function of the average

$$
\mathbb{E}[\alpha] = \alpha
$$
$$
\mathbb{E}[\alpha X] = \alpha \mathbb{E}[X]
$$
$$
\mathbb{E}[\alpha X + \beta] = \alpha \mathbb{E}[X] + \beta
$$
$$
E[X+Y+Z]=E[X]+E[Y]+E[Z]
$$
- Above does not require random variables to be independent
- When
$$
\alpha, \beta = constants + X = random  variable
$$
- You can not reason on the average or the expectation when you are dealing with non linear things
- If X, Y are independent
$$
E[XY] = E[X]*E[Y]
$$
$$
E[g(X)h(Y)] = E[g(X)]*E[h(Y)]
$$
---
Links ::  [[Probability]] [[Expectation]]
Reference :: [[Discrete Random Variables Lecture]]
Type :: #atom
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2024-04-24 14:17
