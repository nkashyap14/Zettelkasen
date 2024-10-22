# Run a Script as a Command job

## Notes:

- Need to configure and submit the job
	- use the command function from python sdk
		- need to specify
			- code: folder that includes the script to run
			- command: specifies which file to run
			- environment: necessary packages to be installed on the compute before running the command
			- compute: specific compute instance to use
			- display_name: name of the individual job
			- experiment_name: name of the experiment the job belongs to
				- All jobs with the same experiment name will be grouped under the same experiment




```
from azure.ai.ml import command

job = command(
	code="./src",
	command="python train.py",
	environment="AzureML-sklearn-0.24-ubuntu18.04-py37-cpu@latest",
	compute="aml-cluster",
	display_name="train-model",
	experiment_name="train-classification-model"
)

returned_job = ml_client.create_or_update(job)
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
Date :: 2024-10-15 17:59