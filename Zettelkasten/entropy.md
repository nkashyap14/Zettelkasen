# entropy

- Characterizes the impurity of an arbitrary collection of examples
- Givven a collection S containing positive and negative examples of some target concept entropy of S is 
- p_pos = proporition of positive examples in S
- p_neg = proportion of negativve examples in S
- 0 log 0 = 0
$$
Entropy(S) = -p_{pos}log_2p_{pos} - p_{neg}*log_2p_{neg}
$$

- Entropy is 0 if all members belong to same class
- Ranges between 0 and 1
- Specifies the minimum number of bits of information needed to encode the classification of an arbitrary member of S
- If S can take on c values then formula is 
- where p_i is the proportion of s belonging to class i
- Logarithm is still base 2 because entropy is a measure of the expected encoding length in bits
$$
Entropy(S) = \sum^{c}_{i=1}-p_i*log_2p_i
$$
---
Links :: [[Computer Science]] [[Statistics]]
Reference :: [[Chapter 3 Decision Tree Learning]] [[Machine Learning by Tom Mitchell]]
Type :: #atom
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2025-05-21 20:12
