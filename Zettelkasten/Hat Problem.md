# Hat Problem

- n people throw their hats in a box and pick one at random
- X = number of people who get their own hat
- find E[X]
- Xi = 1 if i selects own hat 0 otherwise
$$
X = X_1+X_2+...+X_N
$$
- We use the above decomposition of the X random variable into constituent random variables for each ith person as an [[indicator variable]] and then calculate the expected variable fro those variables and then sum that up to get expectation of the total random variable
$$
P(X_i = 1) = 1/n
$$
$$
E[X_i]= (1 * 1/n) + (0 * (1 - 1/n)) = 1 /n
$$
- Are Xi independent? no
- Expectation of the sum of random variables is always the sum of its constitutent expectations 
$$
E[X] = \sum E[X_i] = n * 1/n = 1
$$
$$
E[X]^2 = (1)^2 = 1
$$
$$
Var(X) = E[X^2] - E[X]^2 = E[X^2] - 1 = 2 - 1 = 1
$$
$$
X^2 = (\sum X_i)^2 + \sum_{i,j:i\ne{j}}X_iX_j
$$
$$
E[X_i^2] = E[X_i] = 1/n 
$$
$$
E[X^2] = n *1/n  + ((1/n)(1/n-1)(n^2 - n)) = 2
$$
---
Links ::]] [[Expectation]] [[Properties of Expectation]]
Reference :: [[Discrete Random Variables III Lecture]]
Type :: #atom
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2024-04-28 11:01
