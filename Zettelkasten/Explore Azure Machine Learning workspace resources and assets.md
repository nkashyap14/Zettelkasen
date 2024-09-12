# Explore Azure Machine Learning workspace resources and assets

## General Details

- To use resources and assets from Azure Machine learning need to create an [[Azure Machine Learning workspace resource]] in your [[Azure Subscription]]
	- There you can manage data, [[compute]] resources,[[model|models]], [[Endpoint|endpoints]], and other artifacts
	- Other resources are also automatically provisioned
	- [[Azure Storage Account]]
		- To store files and notebooks used in workspace
		- To store metadata of jobs and models
	- [[Azure Key Vault]]
		- to securely manage secrets like [[authentication keys]] and credentials
	- [[Application Insights]]
		- to monitor predictive services in the workspace
	- [[Azure Container Registry]]
		- created when needed to store images for Azure Machine Learning environments
- First need to create an [[Azure Machine Learning service]] to create a workspace
- Can run [[Jupyter notebooks]]
	- They are stored in the file share of the Azure Storage Account created with the workspace
	- To run notebooks suggested to use a compute instance
- Can run a [[script]] as a job
	- All inputs and outputs get stored in the workspace
- Types of jobs:
	- Command: Execute a single script
	- Sweep: Perform [[hyperparameter]] tuning when executing a single script
	- Pipeline: Run a pipeline consisting of multiple scripts or [[Azure Machine Learning assets|components]]
## Subsections

- [[Ways to create Azure Machine Learning Workspace]]

## Terms defined

- [[AzureML Data Scientist]]
- [[AzureML Compute Operator]]
- [[Azure Machine Learning resources]]
- [[Azure Machine Learning assets]]
- [[Automated Machine Learning]]

Type :: #topic
Links :: [[DP-100]] [[Azure Machine Learning]]
Book :: 
Date ::  2024-09-10 10:39