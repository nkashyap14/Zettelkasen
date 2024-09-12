# Azure Machine Learning assets

## Definition:

- Models
	- End product is the trained model
	- Can train with [[sklearn]] or [[pytorch]]
	- Common way to store is to package as a [[python pickle file]]
	- Can use [[MLflow]] to store in [[MLModel]] format
	- [[Binary Format]] is the way the files are represented and any corresponding [[metadata]]
	- Name + version specified
- Environments
	- Name + version specified
	- Specifies software packages, environment variables, and software settings to run scripts
	- Stored as an image in an [[Azure Container Registry]] when created for the first time
	- When we run a script specify the environment that needs to be used by the compute
- Data Assets
	- Specific file or folder
	- Use these to easily access data every time
	- Name and version specified
- Components
	- Makes it easier to share code
	- Specify name, version, code and enviroinment needed to run code
	- Can represent a step in a [[pipeline]]
---
Links :: [[DP-100]] [[Computer Science]] [[Cloud]]
Reference ::  [[Azure]]
Type :: #definition
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2024-09-10 10:54