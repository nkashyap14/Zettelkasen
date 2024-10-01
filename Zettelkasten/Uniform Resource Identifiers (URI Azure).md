# Uniform Resource Identifiers (URI Azure)

## Definition:

- References t he location of your data
- For [[Azure Machine Learning]] to connect to data need to prefix the URI with the appropriate [[Protocol|protocol]]
	- [[HTTPS]]
		- Used for [[Datastores]] publicly or privately in [[Azure Blob Storage]] or publically available https location
	- [[abfs(s)]]
		- Used for data stores in an [[Azure Data Lake Storage (Gen 2)]]
	- [[azureml]]
		- Used for data stored in a datastore
		- Connection information stored with the data store is used by Azure Machine learning so no need to authenticate
---
Links :: [[DP-100]] [[Computer Science]] [[Cloud]]
Reference ::  [[Azure]]
Type :: #definition
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2024-09-16 16:14