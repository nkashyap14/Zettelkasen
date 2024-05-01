# Binomial Distribution

- X = # of successes in n independent trials
- p = probability of success p
$$
E[X] = \sum_{k=0}^nk\binom{n}{k}p^k(1-p)^{n-k}
$$
- Xi = 1 if success, 0 if fail in trial i
	- Known as an [[indicator variable]]
$$
E[X_i] = (1 * p) + (0 * (1- p)) = p
$$
$$
E[X]= n * p *
$$
$$
Var(X_i)= E[X_i^2] - E[X_i]^2 = p - p^2 = p(1- p)
$$
$$
Var(X)= n*p(1-p)
$$
- Above holds due to [[Properties of Expectation]] where the variance of the sum of independent random variables is the sum of the variances
---
Links :: [[Computer Science]] [[Probability]] [[binomial probability]]
Reference :: [[Discrete Random Variables III Lecture]]]
Type :: #atom
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2024-04-28 10:54
