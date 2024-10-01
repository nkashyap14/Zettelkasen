# Conda Specification file (Azure Custom Environments)

```
name: basic-env-cpu
channels:
  - conda-forge
dependencies:
  - python=3.7
  - scikit-learn
  - pandas
  - numpy
  - matplotlib
```

```
from azure.ai.ml.entities import Environment

env_docker_conda = Environment(
	image="mcr.microsoft.com/azureml/openmpi3.1.2-ubuntu18.04",
	conda_file="./conda-env.yml",
	name="docker-image-plus-conda-example",
	description="Environment created from a Docker image plus Conda environment.",
)

ml_client.environments.create_or_update(env_docker_conda)
```
- This would add python3.7, sklearn, pandas, numpy and matplotlib
- Channel being the location where the packages are stored. The base for hosting and managing packages
- Above takes the base openmpi-3.1.2-ubuntu18.04 microsoft image and adds the custom specification from conda-env
---
Links :: [[#Example Code]] [[Computer Science]] [[DP-100]] [[Custom Environments (Azure Machine Learning)]]
Reference ::
Type :: #code
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2024-09-30 06:06
