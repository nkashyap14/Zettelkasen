# Configure an AutoML Experiment (Code)

```
from azure.ai.ml import automl

classification_job = automl.classification(
	compute="aml-cluster",
	experiment_name="auto-ml-class-dev",
	training_data=my_training_data_input,
	target_column_name="Diabetic",
	primary_metric="accuracy",
	n_cross_validations=5,
	enable_model_explainability=True
)
```

- my_training_data_input refers to a [[MLTable data asset]] 

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
