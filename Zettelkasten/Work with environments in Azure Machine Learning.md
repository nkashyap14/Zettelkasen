# Work with environments in Azure Machine Learning

## General Details

- Environments list and store the necessary packages that you can reuse across compute targets
	- Doesn't refer to devops concept of environments which is a collection of resources used for a specific phase in application deployment
	- Important because experiments may run across various compute contexts
- Two types of environments
	- Curated:
		- Automatically created and made available to you when you create an [[Azure Machine Learning workspace resource]]
	- Custom
		- Created and managed by self. Registered in workspace
		- Makes it possible to define consistent and reusable runtime environments for experiments regardless of the compute target
- Builds environment definitions using [[Docker]] into [[Docker images]] and [[conda environments]]
- Builds the environment definitions in the [[Azure Container Registry]] resource associated with the workspace
## Subsections

## Terms defined

- [[Environment (Azure Machine Learning)]]
- [[Curated Environments (Azure Machine Learning)]]
- [[Custom Environments (Azure Machine Learning)]]

Type :: #topic
Links :: [[DP-100]] [[Azure]] [[Cloud]] [[Computer Science]]
Book :: 
Date ::  2024-09-30 05:50