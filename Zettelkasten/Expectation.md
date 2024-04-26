# Expectation

- Represents the center of gravity in a [[Probability Mass Function|PMF]]
- In probability theory, the expectation of a random variable is a measure of its central tendency or average value, capturing the long-term behavior of the variable over repeated trials. 

$$
\mathbb{E}[X] = \sum_{i} x_i P(X = x_i)
$$
```
\begin{center}
\textbf{Explanation:}
\end{center}

The expectation (mean) of a discrete random variable \( X \), denoted by \( \mathbb{E}[X] \), is calculated as the sum of each possible value of \( X \) multiplied by its corresponding probability.

\[
\mathbb{E}[X] = \sum_{i} x_i P(X = x_i)
\]

In this formula:

\begin{itemize}
    \item \( x_i \) represents each possible value of \( X \).
    \item \( P(X = x_i) \) represents the probability mass function (PMF) of \( X \) evaluated at \( x_i \).
    \item The summation symbol \( \sum \) indicates that we sum over all possible values of \( X \), represented by the index \( i \).
    \item So, we sum the product of each value of \( X \) and its corresponding probability.
\end{itemize}

```
- [[Properties of Expectation]]
- [[Conditional Expectation]]
---
Links :: [[Computer Science]] [[Probability]]
Reference :: [[Discrete Random Variables Lecture]]
Type :: #atom
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2024-04-24 14:11
