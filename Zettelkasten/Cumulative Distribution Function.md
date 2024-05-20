# Cumulative Distribution Function

- Represents the probability that some [[random variable]] takes a value less than or equal to x
- CDF is the  integral of the density under the curve so the density is just the derivative of the CDF
	- So the density is just the rate of accumulation of probability
$$
\frac{dF_X}{d_X}(x)=f_X(x)
$$
		- Derivative of the CDF is equal to the density
- [[Continuous Random Variables]]
$$
F_X(x) = P(X <= x) = \int_{-\infty}^\infty f_X(t)dt
$$
- [[Discrete Random Variable]]
$$
F_X(x) = P(X <= x) = \sum_{k<=x}p_X(k)
$$
---
Links :: [[Probability]] [[Statistics]] [[Distribution]]
Reference :: [[Continuous Random Variables]]
Type :: #atom
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2024-05-14 12:02
