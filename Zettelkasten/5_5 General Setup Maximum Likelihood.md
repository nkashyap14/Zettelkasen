# 5_5 General Setup Maximum Likelihood


### Problem Statement

- Consider a set of m examples 
	- Drawn from p_data(x) which is an unknown data-generating distribution
$$
p_{data}(x) \rightarrow\mathbb{X} = \{x^{(1)}, \dots,x^{(m)}\} 
$$

- Let p_model(x; theta) be a [[parametric model|parametric]] family of [[probability distributions]] over the same space indexed by theta.
	- It maps any configuration x to a real number which estimates the true probability p_data(x)
$$
p_{model}(x;\theta)
$$

- The maximum likelihood estimator is defined to be

$$
\theta_{ML} = \operatorname*{argmax}_{\theta}p_{model}(\mathbb{X}; \theta)= \operatorname*{argmax}_{\theta}\prod_{i=1}^m p_{model}(x^{(i)}; \theta)
$$
	- Basically what this says is that the set of parameters that maximize [[Likelihood Function|likelihood]], probability of our data conditioned on a world where our set of parameters are true, is the set of parameters that maximize the quantity above.
	- The quantity above is a cumulative product over all m samples in our dataset and the value being multiplied is the probability that our model assigns to the sample given said set of parameters.
	- We seek to maximize this quantity because we know these samples come from our true data generating process, [[Empirical Distribution]], so we wish to get the set of parameters that assign the greatest probability to the joint distribution over all these samples.
	- This also assumes that the samples drawn fulfill the assumption of [[Independence|independent and identically distributed]]
	- Issue is this product over large amounts of probabilities can be inconvenient from the programmers point of view. One reason being that it can be prone to numerical underflow
	- Thusly we take the logarithm of the likelihood as it doesn't change the argmax but does have the unique [[properties of logarithms|property]] that it changes products into sums
- Thus it becomes
$$
\theta_{ML} = \operatorname*{argmax}_{\theta} \sum_{i=1}^m log [p_{model}(x^{(i)};\theta)]
$$
	- [[Argmax]] also has the property that if we rescale all values by a constant value it will not change the actual set of theta parameters that maximizes. As such we divide by m to get a version that can be stated as an expectation
- Finally it becomes

$$
\theta_{ML} = \operatorname*{argmax}_{\theta} \mathbb{E}_{x \textasciitilde \hat{p}_{data}} log [p_{model}(x;\theta)]
$$

	- So what this says is we seek the set of theta parameters that maximize the expectation, over all instances of x drawn from our empirical distribution p_hat, of the logarithm of the probability that the model ascribes to the samples at hand!
- [[KL Divergence]]
- Another way we can interpret this is as minimizing the dissimilarity between the empirical distribution p_hat, which again is defined by the training data, and our model's distribution as measured by KL Divergence
- This is given by
$$
D_{KL} (\hat{p}_{data}||p_{model}) = \mathbb{E}_{x\textasciitilde\hat{p}_{data}}[log(\hat{p}_{data}(x)) - log(p_{model}(x))]
$$

		- The term on the left is a function of the data generating process
		- So when we train the model to minimize, because our parameters only minimize the right term that means we only need to minimize the right term aka

$$
- \mathbb{E}_{x\textasciitilde \hat{p}_{data}} [log (p_{model}(x))]
$$

- This is the same as the arg max from two equations ago. So basically we minimize the negative log probability of the data! Aka we minimize the negative log likelihood.
- This is also the equivalent of minimizing the cross entropy between the distributions
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

