
```
import mlflow

mlflow.set_experiment(experiment_name="heart-condition-classifier")
```

- Autologging is a feature that can be enabled that tells the framework to log all metrics, parameters, artifacts, and models the framework considers relevant

```
from xgboost import XGBClassifier

with mlflow.start_run():
	mlflow.xgboost.autolog()

	model = XGBClassifier(use_label_encoder=False, eval_metric="log_loss")
	model.fit(X_train, y_train, eval_set[(X_test, y_test)], verbose=False)
```

- autolog() leads MLFlow to start a run within an experiment and track it
	- can then review all logged metrics in the studio
- Custom Logging can be used in conjunction with autologging and is used to log supplementary or custom information
	- mlflow.log_param(): single key vaule param. used to log input params
	- mlflow.log_metric(): single key value metric, value must be a number. used to log output
	- mlflow.log_artifact(): logs a file, use the function for plots to log saved as image files first
	- mlflow.log_model(): logs a model. Use this function to create a MLFlow model
```
from xgboost import XGBClassifier
from sklearn.metrics import accuracy_score

with mlflow.start_run():
	model=XGBClassifier(use_label_encoder=False, eval_metric="logloss")
	model.fit(X_train, y_train, eval_set=[(X_test, y_test)], verbose=False)
	y_pred = model.predict(X_test)

	accuracy = accuracy_score(y_test, y_pred)
	mlflow.log_metric("accuracy", accuracy)
```
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