# Issues in Decision Tree Learning

- If too much noise in data or number of training examples too small to produce a representative example of the true target function then ID3 produces trees that [[overfit]] training examples
- Definition:
	- $$h, h' \in H$$
	- h overfits training data if alternative training hypothesis h' exists that has smaller error over entire distribution of instances but h has lower error over training examples
	- H is hypothesis space
- Approaches to avoid overfitting:
	- Stop growing the tree earlier before it perfectly classifies data
	- Allow tree to overfit the data but then postprune the tree
		- more successful in practice
- Reduced Error Pruning (Quinlan 1987)
	- Pruning a decision node consists of removing a subtree rooted at that node
	- Making it a leaf node
	- Assigning it to the most common classification of the training examples associated with that node
	- Only remove node if pruned tree performs no worse than original over validation set
	- Prune node that increases accuracy over validation set most
	- Stop when pruning is no longer viable
- Rule Post Pruning:
	- Infer decision tree from training set, allow overfitting to occur
	- Convert the learned tree into an equivalent set of rules by creating one rule for each path from the root node to a leaf node
	- Prune (generalize) each rule by removing any preconditions that result in improving its estimated accuracy
	- Sort pruned rules by estimated accuracy and consider them in sequence when classifying subsequent instances
	- One rule for each leaf node in the tree
	- Each attribute test along the path from root to leaf is a rule antecedent (precondition)
	- Classification at the leaf node becomes the rule consequent (postcondition)
- There is a natural bias in information gain that favors attributes with many values over those with few
	- Take date. Would result in a root node with alot of paths each of those which has small subsets of training examples
	- because of that has high information gain but in reality is not very explanatory and will poorly generalize
	- Can fix this by selecting decision attributes based on some measure other than information gain
	- Can do this via [[gain ratio]]
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

