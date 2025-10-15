# gain ratio

- Penalizes attributes like date by incorporating a term called split information that is sensitive to how broadly and uniformly the attribute splits the data
- S1 -Sc are the c subsets of examples resulting from partitioning S by the c valued attribute A
$$
SplitInformation(S, A) = - \sum^c_{i=1}\frac{|S_i|}{|S|}log_2\frac{|S_i|}{|S|}
$$

- Split information is the entropy of S with respects to the values of attribute A
	- contrasts with the previous use of [[entropy]] with respect to the target attribute whose value is to be predicted by the learned tree
- Gain Ratio is
$$
GainRatio(S, A) = \frac{Gain(S, A)}{SplitInformation(S, A)}
$$
---
Topics :: [[Decision Tree]] [[Machine Learning by Tom Mitchell]] [[Computer Science]]
Reference :: [[Chapter 3 Decision Tree Learning]]
Type :: #molecule
Creator ::
Rating ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2025-05-21 20:02

