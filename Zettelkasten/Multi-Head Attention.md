# Multi-Head Attention

## Definition:

- Laymans terms:
	- Instead of doing [[Attention Function]] once it is done multiple times in parallel and then the results are combined
	- Start with the input data (queries, keys, and values)
	- Create multiple heads which does its own version of a linear transformation of the queries keys and values and then performs attention on these transformed versions
	- Allows different heads to focus on different relationships ie focus on nearby words, other looks at related concepts etc
$$
MH(Q,K,V) = Concat(h_1,...,h_h)W^O
$$
- Where
$$
h_i = Attention(QW^Q_i, KW^K_i, VW^V_i)
$$
---
Links :: 
Paper ::  [[Attention Is All You Need]]
Type :: #paperdefinition
Date :: 2024-09-07 10:44