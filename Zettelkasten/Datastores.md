# Datastores

## Azure Definition:
- Reference to an existing [[Azure Storage Account]]
	- May be referring to [[Azure Blob Storage]] or even [[Azure Data Lake Storage (Gen 2)]]
- Abstractions for cloud data sources within [[Azure Machine Learning]]
	- Encapsulate information needed to connect to data sources and securely store the connection information so that there is no need to code it within state
- Benefits:
	- Easy to use [[Uniform Resource Identifiers (URI Azure)]]
	- Facilitates data discovery
	- Doesn't expose secrets and kiieys to users
- Available authentication methods:
	- Credential Based
		- [[Service Principal]]
		- [[Shared Access Signature (SAS) token]]
		- [[Account Key]]
	- Identity Based
		- [[Microsoft Entry identity]]
		- [[Managed Identity]]
- Types:
	- [[Azure Blob Storage]]
	- [[Azure File Share]]
	- [[Azure Data Lake Storage (Gen 2)]]
- Every [[Azure Machine Learning workspace resource]] has 4 built in datastores
	- 2 connecting to blob containers
	- 2 connecting to azure storage file shares
	- These are used as system storages
- [[Creating Datastore (AZURE CODE)]]
---
Links :: [[DP-100]] [[Computer Science]] [[Cloud]]
Reference ::  [[Azure]]
Type :: #definition
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2024-09-16 16:16