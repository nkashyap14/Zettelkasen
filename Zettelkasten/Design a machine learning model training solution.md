# Design a machine learning model training solution

## General Details

- 6 steps to train a model:
	- Define the problem
		- What should the model predict
		- what defines success
		- What output should be
		- What type of [[Machine Learning Task]] to use
	- Get the data
	- Prepare the data
		- Clean and transform the data based on model requirements
	- Train the model
		- Choose the algorithm and hyperparameters
		- Based on trial and error
	- Integrate the model
		- Deploy it to an endpoint to generate predictions
	- Monitor the model
- Services to train models:
	- [[Azure Machine Learning]]
		- Offers a UI experience via studio
		- Can use python sdk to manage workloads
		- Or use the CLI for a code-first expierence
	- [[Azure Databricks]]
		- Data analytics platform can be used for data engineering and data science
		- Uses a distributed [[Spark Clusters]] to efficiently process data
		- Can integrate with other services like [[Azure Machine Learning]]
	- [[Azure Synapse Analytics]]
		- analytics services which uses distributed compute for big data analytics
		- Designed to ingest and transform data at scale primarily but also includes several ML capabilities
		- Can train models on spark pools with MLlib or use integrated automated machine learning feature from [[Azure Machine Learning]]
	- [[Azure AI Services]]
		- Collection of prebuild machine learning models that can be used for common machine learning tasks like object detection in images
		- Can save time and effort
- Reasons to use services:
	- Time and effort can be saved via azure AI services
	- Azure Synapse Analytics or Databricks when you want to keep data-related projects within the same service
		- Or if you want distributed computes for large workloads
		- Will work with [[Pyspark]]
	- Use Azure Machine Learning or DataBricks when you want full control over model training and management
	- Azure ML when python is preferred programming language
	- Azure ML when you want a UI
- Compute Options:
	- Most valuable resource is compute
	- [[CPU]]
		- Better for smaller tabular datasets
	- [[GPU]]
		- Might be better on larger tabular datasets too
		- Higher Cost
	- Virtual Machine Size Options:
		- [[General Purpose SKU]]
		- [[Memory Optimized SKU]]
	- [[Spark Clusters]]
		- Use same sizing as VM's but distribute workloads
## Subsections

## Terms defined


Type :: #topic
Links :: [[DP-100]] [[Azure]] [[Cloud]]
Book :: 
Date ::  2024-09-08 07:28