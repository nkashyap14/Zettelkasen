# Create and use a compute instance

```
from azure.ai.ml.entities import ComputeInstance

ci_basic_name = "basic-ci-12345"
ci_basic =  ComputeInstance(
	name=ci_basic_name,
	size="STANDARD_DS3_v2"
)
ml_client.begin_create_or_update(ci_basic).result()
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
