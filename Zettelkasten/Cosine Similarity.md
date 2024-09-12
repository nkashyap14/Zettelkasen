# Cosine Similarity

## Definition:
- Used to find similarities between data observations
- A [[data observation]] with numeric features is just a vector of real numbers
- Used in [[Mathematics]] as a similarity metric for real-valued [[vector|vectors]]
- Takes value between -1 and 1
- Measures proportional similarity of feature values
	- Ratio between feature columns
- 1 = greater similarity
- -1 = greater divergence
- 0 = no correlation (neither similar nor dissimilar)

$$
cossim(u, v) = \frac{u}{||u||_2} .\frac{v}{||v||_2}
$$
- Denominators are [[L2 norm|L2 norms]]
- [[Cosine Similarity sklearn]]
---
Links ::  [[Computer Science]] [[Machine Learning]] [[similarity]] [[Clustering]]
Reference ::  [[Educative]]
Type :: #definition
Discussion ::
Date :: 2024-09-10 19:48