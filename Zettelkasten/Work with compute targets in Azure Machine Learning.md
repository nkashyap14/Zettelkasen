# Work with compute targets in Azure Machine Learning

## General Details

- Types of compute:
	- Compute instance: similar to a [[virtual machine]] and is primarily used for notebooks. Idea for experimentation
	- Compute Clusters: Multi-node clusters of virtual machines that automatically scale up or down to meet demand. Cost effective way to run scripts that need to process large volumes of data. Allow you to use [[parallel processing]]
	- Kubernetes Cluster: Gives more control on how compute is configured and managed. Can attach your own self-managed [[Azure Kubernetes Service (AKS)]] cluster or use an Arc Kubernetes cluster for on-premises workloads
	- Attached Compute: Can attach existing compute like Azure Databricks clusters or Azure VM's to workspace
	- Serverless compute: Fully managed, on demand compute for training jobs
- A compute instance can be assigned to only one user as it can't run parallel workloads
- Stop compute instances when not using them to save costs
## Subsections

- [[Create and use a compute instance]]
- [[Create and use a compute cluster]]
## Terms defined

- [[Compute Targets]]


Type :: #topic
Links :: [[DP-100]]
Book :: 
Date ::  2024-09-18 10:01