# Probability Mass Function

- A Probability Mass Function (PMF) is a function that assigns probabilities to discrete random variables, representing the probability that a discrete random variable takes on a specific value.
- Some numerical values are more likely to occur than some other numerical values and captured that by representing probabilities for them
- Represents for discrete values not continuous values
- All concrete probabilities are non negative
- Total probability for a pmf sums to 1
- Represents a probability distribution of a [[Random Variable]]
$$
p(X = x_i) = \begin{cases}
    p_1 & \text{if } i = 1, \\
    p_2 & \text{if } i = 2, \\
    \vdots & \vdots \\
    p_n & \text{if } i = n,
\end{cases}
$$
$$
p(X = k) = (1 - p)^{k-1} \cdot p \quad \text{for } k = 1, 2, 3, \ldots
$$
- P(X=k) denotes the probability that the first head occurs on the k-th toss.
- (1−p)^k−1 represents the probability of getting k−1 consecutive tails followed by one head.
- p is the probability of getting a head on any single toss.
- This is an example of a [[geometric pmf]]
---
Links :: [[Computer Science]]
Reference :: [[Discrete Random Variables Lecture]]
Type :: #atom
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2024-04-24 13:27
