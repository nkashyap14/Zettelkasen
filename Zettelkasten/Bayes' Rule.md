# Bayes' Rule

## Summary

$$[ P(B \mid A) = \frac{P(A \mid B) P(B)}{P(A)} $$


```
# Bayes' Theorem

Bayes' Theorem is a fundamental theorem in probability theory. It describes the probability of an event, based on prior knowledge of conditions that might be related to the event. This theorem is especially powerful in conditional probability and decision-making processes.

## The Formula

Bayes' Theorem is expressed by the following formula:

$$
P(B \mid A) = \frac{P(A \mid B) P(B)}{P(A)}
$$

where:
- **$P(B \mid A)$** is the probability of event $B$ given that event $A$ has occurred.
- **$P(A \mid B)$** is the probability of event $A$ given that event $B$ has occurred.
- **$P(B)$** and **$P(A)$** are the probabilities of observing $B$ and $A$ independently of each other.

## Example

Assume there are two events, $A$ and $B$. Event $A$ occurs with probability 0.3, and event $B$, given $A$, occurs with a probability of 0.7. The probability of $B$ occurring independently is 0.5. Using Bayes' Theorem, the probability of $A$ given $B$ is calculated as follows:

$$
P(A \mid B) = \frac{0.7 \times 0.3}{0.5} = 0.42
$$

Thus, the probability of $A$ given that $B$ has occurred is 0.42.


```

$$ P(A \mid B) = \frac{P(B \mid A) P(A)}{P(B)} $$

$$
 P(A_i \mid B) = \frac{P(B \mid A_i) P(A_i)}{\sum_{j=1}^n P(B \mid A_j) P(A_j)} 
$$

$$
 P(A_i \mid B) = \frac{P(B \cap A_i)}{\sum_{j=1}^n P(B \mid A_j) P(A_j)} 
$$
$$
 P(A_i \mid B) = \frac{P(B \cap A_i)}{P(B)} 
$$
## Details
- Cause and effect. Given a current effect we want to calculate the likelihood of a certain cause being the reason that the effect was observed

## Conclusion


Type :: #topic
Links :: [[Probability]] [[Statistics]] [[Conditional Probability]]
Creator ::
Date ::  2024-04-17 12:22