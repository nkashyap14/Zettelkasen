# 5_8_1 Principal Components Analysis Derivation

### Problem Statement

- Consider a m x n design matrix X. Assume the data as a mean of 0 (This can easily be done by just subtracting the mean of the data from all the examples at a preprocessing step.)
- Unbiased Sample Covariance Matrix associated with X is given by
$$
Var[x] = \frac{1}{m - 1}X^TX
$$

- PCA finds a representation via  alinear transformation z = W^T * X where Var[z] is diagonal
- Note that the principle components of a design matrix are given by the eigenvectors of X^T*X
	- So it follows that the eigen decomposition is
$$
X^TX=W\Lambda W^T
$$
---
Topics ::  [[Deep Learning]]
Reference ::
Type :: #molecule
Creator ::
Rating ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2025-10-01 20:36

