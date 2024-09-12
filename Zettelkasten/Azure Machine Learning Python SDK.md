# Azure Machine Learning Python SDK

```
pip install azure-ai-ml
```

- Authentication
	- Requires 3 params:
		- subscription_id
		- resource_group
		- workspace_name
```
from azure.ai.ml import MLClient
from azure.identity import DefaultAzureCredential

ml_client = MLClient(
	DefaultAzureCredential(), subscription_id, resource_group, workspace
)
```

- From there call the MLClient for the environment to connect to the workspace
```
from azure.ai.ml import command

#configure job
job = command(
	code="./src",
	command = "python train.py",
	environment ="AzureML-sklearn-0.24-ubuntu18.04-py37-cpu@latest",
	compute="aml-cluster",
	experiment_name="train-model"
)

#connect to workspace and submit job
returned_job = ml_client.create_or_update(job)
```
---
Links :: [[#Example Code]] [[Computer Science]] [[DP-100]]
Reference ::
Type :: #code
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2024-09-10 12:59
