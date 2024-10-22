# Use a Sweep Job For Hyperparameter Tuning

## Notes:

- Training script utilized similar for any training jobs except
	- Script must include an argument for each hyperparameter you want to vary
	- Log the target performance metric with MLFlow
		- Logged metric enables the sweep job to evaluate the performance of the trials it initiates
```
import argparse
import pandas as pd
import numpy as np
from sklearn.model_selection import train_test_split
from sklearn.linear_model import LogisticRegression
import mlflow

# get regularization hyperparameter
parser = argparse.ArgumentParser()
//note the regularization argument to set the regularization hyperparameter, this enables the sweep job to tune on regularization rate
parser.add_argument('--regularization', type=float, dest='reg_rate', default=0.01)
args = parser.parse_args()
reg = args.reg_rate

# load the training dataset
data = pd.read_csv("data.csv")

# separate features and labels, and split for training/validatiom
X = data[['feature1','feature2','feature3','feature4']].values
y = data['label'].values
X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.30)

# train a logistic regression model with the reg hyperparameter
model = LogisticRegression(C=1/reg, solver="liblinear").fit(X_train, y_train)

# calculate and log accuracy
y_hat = model.predict(X_test)
acc = np.average(y_hat == y_test)
//note logging of accuracy
mlflow.log_metric("Accuracy", acc)
```

```

//to prepare teh sweep job must first create a base command job that specifies which script to run and defines the parameters used by the script
from azure.ai.ml import command
job = command(
	code="./src",
	command="python train.py --regularization ${{inputs.reg_rate}}",
	inputs={
		"reg_rate": 0.01
	},
	environment="AzureML-sklearn-0.24-ubuntu18.04-py37-cpu@latest", 
	compute="aml-cluster",
)

//then override the input parameters with a search space

from azure.ai.ml.sweep import Choice

command_job_for_sweep = job(
    reg_rate=Choice(values=[0.01, 0.1, 1]),
)

//then call sweep on the comamnd job to sweep over the search space
from azure.ai.ml import MLClient

# apply the sweep parameter to obtain the sweep_job
sweep_job = command_job_for_sweep.sweep(
    compute="aml-cluster",
    sampling_algorithm="grid",
    primary_metric="Accuracy",
    goal="Maximize",
)

# set the name of the sweep job experiment
sweep_job.experiment_name="sweep-example"

# define the limits for this sweep
sweep_job.set_limits(max_total_trials=4, max_concurrent_trials=2, timeout=7200)

# submit the sweep
returned_sweep_job = ml_client.create_or_update(sweep_job)
```
---
Links :: [[DP-100]] [[Computer Science]] [[Cloud]]
Reference ::  [[Azure]]
Type :: #definition
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2024-10-16 10:21