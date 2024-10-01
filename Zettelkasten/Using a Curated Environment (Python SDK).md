# Using a Curated Environment (Python SDK)


```
from azure.ai.ml import command

#configure job
job = command(
	code="./src",
	command="python train.py",
	environment="AzureML-sklearn-0.24-ubuntu18.04-py37-cpu@latest",
	compute="aml-cluster",
	display_name="train-with-curated-environment",
	experiment_name="train-with-curated-environment"
)

returned_job = ml_client.create_or_update(job)
```

---
Links :: [[#Example Code]] [[Computer Science]] [[DP-100]] [[Curated Environments (Azure Machine Learning)]]
Reference ::
Type :: #code
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2024-09-30 05:57
