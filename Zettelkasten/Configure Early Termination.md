# Configure Early Termination

## Notes:

- Have to consider time and expense of testing new hyperparameter values
	- Each trial is a new model trained. May want to stop the sweep job early if a new model doesn't result in a significantly better model and then just use the best model so far
- Early termination policy:
	- Can be especially beneficial when working with continuous hyperparameters
		- or with a random or bayesian sampling method
	- Two main parameters:
		- Evaluation_interval:
			- Specifies at which interval you want the policy to be evaluated.
			- Every time the primary metric is logged for a trial counts as an interval
		- Delay_evaluation:
			- specifies when to start evaluating the policy 
			- Allows for a minimum amount of trials to complete without the policy affectingt hem
	- 3 options for early termination:
		- bandit policy: uses a slack_factor (relative) or slack_amount (absolute). Any new model must perform within the slack range of the best performing model
		- Median stopping policy: uses the median of the averages of the primary metric. Any new model must perform better than the median
		- Truncation selection policy: Uses a truncation percentage which is the percentage of lowest performing trials. A new model must perform better than the lowest performing trials

#### Bandit Policy

```
from azure.ai.ml.sweep import BanditPolicy

sweep_job.early_termination = BanditPolicy(
	slack_amount = 0.2,
	delay_evaluation = 5,
	evaluation_interval = 1
)
```

- If after 5 trials best accuracy of a model is .9 any new model must have > .7 accruacy otherwise policy ends the sweep job
- slack_factor would compare the performance metric as a ratio rather than an absolute value
#### Median Stopping policy

- Abandons trials where the target performance metric is worse than the median of the running averages for all trials
```
from azure.ai.ml.sweep import MedianStoppingPoolicy

sweep_job.early_termination = MedianStoppingPolicy(
	delay_evaluation = 5,
	evaluation_interval = 1
)
```
#### Truncation Selection Policy

- A truncation selection policy cancels the lowest performing _X_% of trials at each evaluation interval based on the _truncation_percentage_ value you specify for _X_.

```
from azure.ai.ml.sweep import TruncationSelectionPolicy

sweep_job.early_termination = TruncationSelectionPolicy(
    evaluation_interval=1, 
    truncation_percentage=20, 
    delay_evaluation=4 
)
```

- After 5 trials metric should not be in the 20% bottom or the worst trial for the job to end
---
Links :: [[DP-100]] [[Computer Science]] [[Cloud]]
Reference ::  [[Azure]]
Type :: #definition
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2024-10-16 10:07