# Create a custom environment from a Docker image

```
from azure.ai.ml.entities import Environment

env_docker_image = Environment(
	image="pytorch/pytorch:latest",
	name="public-docker-image-example",
	description="Environment created from a public Docker image.",
)

ml_client.environments.create_or_update(env_docker_image)
```

```
from azure.ai.ml.entities import Environment

env_docker_iamge = Environment(
	image="mcr.microsoft.com/azureml/openmpi3.1.2-ubuntu18.04",
	name="aml-docker-image-example",
	description="Environment created from a Azure ML Docker image."
)

ml_client.environments.create_or_update(env_docker_image)
```

---
Links :: [[#Example Code]] [[Computer Science]] [[Docker]] [[Custom Environments (Azure Machine Learning)]] [[Azure]]
Reference ::
Type :: #code
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2024-09-30 06:01
