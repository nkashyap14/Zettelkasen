# Using a Custom Environment (Python SDK)

```
from azure.ai.ml import Command

job = command(
	code="./src",
	command="python train.py",
	environment="docker-image-plus-conda-example:1",
	compute="aml-cluster",
	display_name="train-custom-env",
	experiment_name="train-custom-env"
	)

#submit_job

returned_job = ml_client.create_or_update(job)
```


---
Links :: [[#Example Code]] [[Computer Science]] [[DP-100]] [[Custom Environments (Azure Machine Learning)]]
Reference ::
Type :: #code
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2024-09-30 06:09
