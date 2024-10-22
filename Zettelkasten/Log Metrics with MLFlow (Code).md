# Log Metrics with MLFlow (Code)

## Code:

```
import mlflow

reg_rate = 0.1
mlflow.log_param("Regularization rate", reg_rate)

// mlflow.log_param() : logs single key value parameter
// mlflow.log_metric(): logs single key value metric. Value must be a number
// mlflow.log_artifact(): logs a file. used to save a plot asa an aimage file
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
Date :: 2024-10-15 21:18