# Azure Machine Learning resources

## Definition:
- Refer to:
	- The workspace
		- Top level resource
		- Need access to this to train + track models and to deploy models to endpoints
	- [[compute]] resources
		- 5 types:
			- Compute instances
				- Similar to a [[virtual machine]] in the cloud
				- Managed by workspace
				- Ideal to use as a development environment to run [[Jupyter notebooks]]
			- Compute clusters
				- On demand clusters of [[CPU]] or [[GPU]] [[compute]] nodes in the cloud managed by workspace
				- Ideal for production workloads as they autoscale
			- [[Kubernetes]] clusters
				- Allows us to create or attach an [[Azure Kubernetes Service (AKS)]] cluster
				- Ideal for production
			- Attached computes
				- Allows us to attach other compute resources like [[Azure Databricks]] or Synapse [[Spark Pools]]
			- [[Serverless compute]]
				- Fully managed on demand compute used for trianing jobs
		- Compute is the most cost intensive
	- [[Datastores]]
		- References to azure data services
		- Connection information to a data service is stored in a [[Azure Key Vault]]
		- 4 datastores automatically added to workspace upon creation:
			- workspaceartifactstore
				- Connects to azureml container of the [[Azure Storage Account]]
				- Used to store compute and experiment logs
			- workspaceworkingdirectory
				- Connects to the file share of the [[Azure Storage Account]] used by the Notebooks
				- When you upload files or folders to access from a compute instance it ends up here
			- workspaceblobstore
				- Connects to [[blob storage]] of the [[Azure Storage Account]]
				- Set as default datastore
				- Connects to azureml-blobstore-... container
			- workspacefilestore:
				- Connects to file share of [[Azure Storage Account]]
				- Connects to azureml-filestore-... fileshare
---
Links :: [[DP-100]] [[Computer Science]] [[Cloud]]
Reference ::  [[Azure]]
Type :: #definition
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2024-09-10 10:48