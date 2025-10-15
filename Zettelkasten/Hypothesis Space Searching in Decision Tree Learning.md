# Hypothesis Space Searching in Decision Tree Learning

- [[ID3 Algorithm]] can be characterized as searching a space of hypotheses for one that fits the training examples
- Space searched is the set of possible decision trees
- Performs a simple-to-complex hill-climbing search through this space
	- Evaluation function is [[Information Gain]]
- Hypothesis space is a complete space of finite discrete-valued functions relative to available attributes
- Maintains only a single current hypothesis as it searches through the space of decision trees
- In its pure form does no backtracking, after using an attribute never backtracks to consider its choice. As such susceptible to the usual risks of [[hill-climbing]] search without backtracking, converging to locally optimal solutions that are not globally optimal
- Uses all training examples at each step in the search to make statistically based decisions regarding how to refine its current hypothesis
	- results in a much less sensitive to errors in individual training examples
	- Can handle nosiy training data
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

