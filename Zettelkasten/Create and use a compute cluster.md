# Create and use a compute cluster

```
from azure.ai.ml.entities import AmlCompute

cluster_basic = AmlCompute(
	name="cpu-cluster",
	type="amlcompute",
	size="STANDARD_DS3_v2",
	location="westus",
	min_instances=0,
	max_instances=2,
	idle_time_before_scale_down=120,
	tier="low_priority",
)

ml_client.begin_create_or_update(cluster_basic).result()
```


- 3 main parameters:
	- size: Specifies virtual machine type of each node in the cluster
	- max_instances: maximum number of nodes to scale to
	- Tier: low priority or dedicated. Low priority is lower costs however you are not guaranteed availability

### Use a compute cluster

- 3 main scenarios when using compute cluster:
	- Running pipeline job built in designer
	- Running an automated machine learning job
	- Running a script as a job
- Compute will scale up in each and then scale down whne job is done
	- First two can be run through the [[Azure Machine Learning studio]]

```
from azure.ai.ml import command

job = command(
	code="./src",
	command="python diabetes-training.py",
	environment="AzureML-sklearn-0.24-ubuntu18.04-py37-cpu@latest",
	compute="cpu-cluster",
	display_name="train-with-cluster",
	experiment_name="diabetes-training"
)

returned_job = ml_client.create_or_update(job)
aml_url=returned_job.studio_url
print("Monitor your job at", aml_url)
```
---
Links :: [[#Example Code]] [[DP-100]] [[Azure Machine Learning Python SDK]]
Reference ::
Type :: #code
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2024-09-18 10:07
