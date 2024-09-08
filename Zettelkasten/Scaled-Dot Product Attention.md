# Scaled-Dot Product Attention

## Definition:

- Input = queries and keys of dimension d_k, values of dimension d_v
- Compute [[dot product]] of the query with all keys
	- Divide each by sqrt(d_k) and apply a [[softmax]] function to obtain the weights on the values
	- K and V are matrices of keys and values
	- Q is a matrix of a set of queries packed together

$$
Attention(Q,K,V) = softmax(\frac{QK^T}{\sqrt{d_k}})V
$$
---
Links :: [[Machine Learning]] [[Attention Function]]
Paper ::  [[Attention Is All You Need]]
Type :: #paperdefinition
Date :: 2024-09-07 10:39