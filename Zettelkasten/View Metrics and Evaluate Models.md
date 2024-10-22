# View Metrics and Evaluate Models

## Definition:

- Can review logged parameters, metrics, and artifacts in Azure Machine Learning studio
	- Find the experiment run and open it to view its details
	- In details tab logged parameters are shown under Params
	- Select metrics tab to see metrics
	- Artifacts as plots are under images
```

//get all active experiments ussing mlflow
experiments = mlflow.search_experiments(max_results=2)
for exp in experiments: 
	print(exp.name)
	//retrieve metrics of a specific run
	mlflow.search_runs(exp.experiment_id)
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
Date :: 2024-10-15 21:20