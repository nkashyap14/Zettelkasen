# Define a search space

## Notes:

- Set of hyperparameter values tried during hyperparameter tuning is known as the search space
- [[Discrete Hyperparameters]]
	- Require discrete values
	- Have a finite set of possibilities
	- Can define a list of explicit values, a range, or an arbitrary set of comma separated values
	- Can also select discrete values from folloowing discrete distributions
		- QUniform(min_value, max_value, q): Returns a value like round(Uniform(min_value, max_value) / q) * q
		- QLogUniform(min_value, max_value, q): Returns a value like round(exp(Uniform(min_value, max_value)) / q) * q
		- QNormal(mu, sigma, q): Returns a value like round(Normal(mu, sigma) / q) * q
		- QLogNormal(mu, sigma, q): Returns a value like round(exp(Normal(mu, sigma)) / q) * q
- [[Continuous Hyperparameters]]
	- Can have similar distributions as to the discrete hyperparameters to choose from
		- - Uniform(min_value, max_value): Returns a value uniformly distributed between min_value and max_value
		- LogUniform(min_value, max_value): Returns a value drawn according to exp(Uniform(min_value, max_value)) so that the logarithm of the return value is uniformly distributed
		- Normal(mu, sigma): Returns a real value that's normally distributed with mean mu and standard deviation sigma
		- LogNormal(mu, sigma): Returns a value drawn according to exp(Normal(mu, sigma)) so that the logarithm of the return value is normally distributed
- Define a search space

```
from azure.ai.ml.sweep import Choice, Normal

command_job_for_sweep = job(
	batch_size=Choice(values=[16, 32, 64]),
	learning_rate=Normal(mu=10, sigma=3)
)
```
---
Links :: [[DP-100]] [[Computer Science]] [[Cloud]]
Reference ::  [[Azure]]
Type :: #definition
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2024-10-16 09:56