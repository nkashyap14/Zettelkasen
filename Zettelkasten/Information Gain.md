# Information Gain


- Measures how well a attribute/feature separates training examples according to target classification
- Uses a measure called [[entropy]]
- Gain(S, A) of an attribute A relative to collection of examples S
- Values(A) is set of all possible values for Attribute A
- S_v is subset of S for which attribute has value A
- First term is Entropy of original Collection
- Second term is expected value of entropy after S is partitioned using A
	- Sum of entropies of each subset S_v weighted by the fraction of examples that belong to S_v

$$
Gain(S, A) = Entropy(S) - \sum_{v \in Values(A)}\frac{|S_v|}{|S|}*Entropy(S_v)
$$

- Information gain is the expected reduction in entropy by knowing the value of attribute A
- Or in another way Gain(S, A) is the information provided about the target function value given the value of some Attribute A. Or the number of bits saved when encoding the target value of an arbitrary member of S by knowing the value of attribute A
---
Links :: [[Computer Science]] [[Statistics]]
Reference :: [[Machine Learning by Tom Mitchell]] [[Chapter 3 Decision Tree Learning]]
Type :: #atom
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2025-05-21 20:12
