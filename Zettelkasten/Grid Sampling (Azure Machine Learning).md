# Grid Sampling (Azure Machine Learning)

## Definition:

```
from azure.ai.mlk.sweep import Choice

command_job_for_sweep = command_job(
	batch_size=Choice(values=[16, 32, 64]), 
	learning_rate=Choice(values=[0.01, 0.1, 1.0]),
)

sweep_job = command_job_for_sweep.sweep(
	sampling_algorithm="grid",
	...
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
Date :: 2024-10-16 10:02