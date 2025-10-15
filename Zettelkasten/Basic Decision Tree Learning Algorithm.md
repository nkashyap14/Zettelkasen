# Basic Decision Tree Learning Algorithm

- Most approaches to decision trees are variations of a core algorithm that does a top-down greedy search through the space of possible decision trees
- Algorithms are [[ID3 Algorithm]] and [[C.45 (Quinlan 1993) Algorithm]] which is ID3's successor
### ID3 Algorithm
- Learns decision trees by constructing them top down by asking which attribute should be tested at the root of the tree
- Use a statistical test to determine
- From there a descendant of the root node is created for each possible value of the attribute
- Training examples are sorted to the appropriate descended node
- Then keep repeating process using training examples
	- Algorithm never backtracks and considers previous choices
- Statistical Property used is [[Information Gain]]

###### Pseudocode
```
ID3(Examples, Target Attribute, Atttributes)
- Create a root node for tree
- If all examples positive return the single root node with label = +
- If all examples negative return the single root node with label = -
- If attributes is empty return the single node tree Root with label = most common value of target attribute in example
- Otherwise begin:
	- A <- Attribute from Attributes that best classifies examples
	- Decision attribute for root <- A
	- For each possible value v_i of A
		- Add a new tree branch below Root corresponding to test A = v_i
		- Let exmaples_v_i be the subset of examples that have value v_i for A
		- if Examples_v_i is empty
			- Then below this new branch add a lead node with lable = most common value of target_attribute in examples
			- Else below this branch add subtree
				- ID3(Examples_v_i, Target_attribute, Attributes - {A})
- End
- Return Root

```
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

