# Probability Density Function

- Complete description of any statistical information that could be interesting for a continuous random variable
- Replaces [[Probability Mass Function]] for the cases of [[Continuous Random Variables]]
- Summation gets replaced by integrals
## Properties:
- One property is that any individual point has 0 probability
	- The density of that point tells us the approximate probability of small intervals. The probability becomes density times delta where delta is a very small number
	- What below tells us is that density is probability per unity length over small intervals of length density
	- Density under the curve can be thought of as a rate of how probability accumulates
$$
\frac{P(x <= X <= x + \delta)}{\delta} = \int_x^{x+\delta}{f_X(x)*dx} \approx f_X(x)
$$
- Area under curve can't be negative
- Probability of the entire line should be 1
![[pdf.jpg]]

$$
P(a <= X <= b)  = \int_{a}^b{f_x(x) * dx}
$$
---
Links :: [[Statistics]] [[Probability Mass Function]] [[Probability]]
Reference :: [[Continuous Random Variables]]
Type :: #atom
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2024-05-10 16:29
