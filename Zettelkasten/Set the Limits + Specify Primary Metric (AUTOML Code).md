
```
from azure.ai.ml.automl import ClassificationPrimaryMetrics

#retrieving the list of metrics available for training a classification model
list(ClassificationPrimaryMetrics)

classificaiton_job.set_limits(
	timeout_minutes=60, #max time for the AutoML experimnt
	trial_timeout_minutes=20, #max time for a trial
	max_trials=5,
	enable_early_termination=True #end if score isn't improving in the short term
)
```


---
Links :: [[AutoML]] [[Computer Science]] [[Azure]] [[Azure Machine Learning]]
Reference ::
Type :: #code
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2024-10-01 14:18
