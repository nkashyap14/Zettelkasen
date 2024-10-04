# Setting up MLFlow (Code)

```
#verifying that the instance has mlflow and integration code
pip show mlflow
pip show azureml-mlflow

#installing necessary mlflow packages
pip install mlflow
pip install azureml-mlflow

#setting MLflow to point ot the Azure Machine Learning workspace
mlflow.set_tracking_uri = "MLFLOW-TRACKING-URI"
```

- Can find the uri on the overview page of the [[Azure Machine Learning workspace resource]]

---
Links :: [[Azure]] [[Computer Science]] [[Azure Machine Learning]] [[MLflow]]
Reference ::
Type :: #code
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2024-10-02 06:25
