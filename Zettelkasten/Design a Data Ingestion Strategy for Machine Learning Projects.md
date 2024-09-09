# Design a Data Ingestion Strategy for Machine Learning Projects

## General Details

- Separate compute from storage
- Compute is scalable and often you don't want compute active to save costs. Separate data so that it isn't lost when compute is down
- Storing Data:
	- [[Azure Blob Storage]]
		- Cheapest option for storing [[Unstructured Data]]
	- [[Azure Data Lake Storage (Gen 2)]]
		- More advanced version of blob storage
		- Stores files like csv files and image files as unstructured data
		- Storage capacity is basically limitless
	- [[Azure SQL Database]]
		- Used for [[Tabular Data]]
		- Good for data that doesn't change over time
		- Requires us to define tables and work with [[SQL]]
- Data Ingestion Pipelines:
	- [[Azure Synapse Analytics]]
		- Can use the data integration feature 
		- Also called Azure Synapse Pipelines
		- Can schedule and create pipelines through UI or by using [[JSON]]
		- Utilizes different types of compute:
			- [[Serverless SQL Pools]]
			- [[Dedicated SQL Pools]]
			- [[Spark Pools]]
	- [[Azure Databricks]]
		- Allows us to define pipelines in a notebook which can then be scheduled to run
		- Uses [[Spark Clusters]]
	- [[Azure Machine Learning]]
		- Provides [[compute clusters]] which can scale up and down as needed 
		- Can create a pipeline with designer tool or by using a collection of scripts 
		- Used to train [[Machine Learning Models]]
		- Used when  you want to perform all tasks in the same pool while synapse analytics and databricks offer more scalable compute that allows for transformations to be distributed across compute nodes
## Subsections

## Terms defined

- [[Unstructured Data]]
- [[Semi-Structured Data]]
- [[Tabular Data]]
- [[Data Ingestion Pipeline]]


Type :: #topic
Links :: [[DP-100]] [[Azure]]
Book :: 
Date ::  2024-09-07 21:24