# Likelihood Function

## Summary

- A type of function that measures the plausibility of a [[statistical model parameter]] given a set of observed data
- Parameters are the unknown values that define the behavior of the statistical model
- Data is the observed values or samples from the population that we are studying
$$
\theta = param, X=Data
$$
- Likelihood function answers the question given the observed data how likely is it that the parameters have specific values
	- used to estimate the parameters of a model based on the observed data
$$
L(\theta|X) = P(X|\theta)
$$
- What above says is that the likelihood function passed in the parameters conditioned on the sample we have seen will output the probability that we see said sample based on the parameters given
## Subtopics

- To estimate the parameters of a model we tend to maximize the likelihood function
	- This method is called [[Maximum Likelihood Estimation]]
		- Parameter values that maximize the likelihood function are considered the best estimates for the model given the data

## Details
- Quantifies how probable the observed data is for different values of the model parameters

## Conclusion


Type :: #topic
Links :: [[Statistics]] [[Mathematics]] [[function]] [[Probability]] [[Standard Normal Distribution]]
Creator ::
Date ::  2024-06-22 12:35