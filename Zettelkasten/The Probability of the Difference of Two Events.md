# The Probability of the Union of the Difference of Two Events

```

```

#### Set up of Problem Space
$$
A, B = Events
$$
$$
C = A \cap B^c, D=B \cap A^c, E= A \cap B
$$
- Prove
$$
P(C \cup D) = P(A) + P(B) - 2*P(E)
$$

#### Mathematical Flow
##### First:
$$
P(C \cup D) = P(C) + P(D) because C\cap D == \emptyset
$$
##### Second:
$$
A = C \cup E ... bc.. (A \cap B) \cup (A \cap B^c) = A \cap (B \cup B^c)
$$
##### Third:
$$
P(A) = P(C) + P(E) .... bc C \cap E = \emptyset
$$
##### Fourth:
$$
P(C) = P(A) - P(E)
$$
##### Fifth:
$$
P(C) + P(D) = P(A) - P(E) + P(D)
$$
##### Sixth:
- Apply preceding logic for D to derive 
$$
P(D) = P(B) - P(E)
$$
##### Seventh:
$$
P(C \cup D) = P(C) + P(D) = P(A) - P(E) + P(D) = P(A) + P(B) - 2*P(E)
$$
---
Links ::  [[Probability]] [[Probability Models and Axioms]]
Reference :: [[MIT]]
Type :: #probabilityproblem
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2024-05-08 15:52