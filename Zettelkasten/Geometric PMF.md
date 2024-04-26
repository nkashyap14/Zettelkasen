# Geometric PMF

- X = number of independent coin tosses until first head
- Below is the probability that the [[Random Variable]] X takes on the value k
$$
P(X = k) = (1 - p)^{k-1} \cdot p \quad \text{for } k = 1, 2, 3, \ldots
$$

$$
E[X] = \sum_{k=1}^\infty k*p_X(k) = \sum_{k=1}^\infty k*(1-p)^{k-1}*p
$$

- Memoryless ness property of geometric distribution
	- What happened in past doesn't affect future
	- Property applies due to assumed [[Independence]]
---
Links :: [[Probability]] [[Probability Mass Function]]
Reference :: [[Discrete Random Variables II Lecture]]
Type :: #atom
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2024-04-26 10:40
