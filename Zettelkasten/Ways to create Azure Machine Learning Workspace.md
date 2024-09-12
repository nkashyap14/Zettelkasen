# Ways to create Azure Machine Learning Workspace

## Definition:

- User interface via Azure Portal
- Use an [[Azure Resource Manger (ARM)]] template
- Use [[Azure Command Line Interface (CLI)]] with the [[Azure Machine Learning CLI extension]]
- Use the [[Azure Machine Learning Python SDK]]
	- Example below
```
from azure.ai.ml.entities import Workspace

workspace_name = "mlw_example"

ws_basic = Workspace(
	name=workspace_name,
	location="eastus",
	display_name="Basic Example Workspace",
	description="HOw to create example workspace",
)

ml_client.workspaces.begin_create(ws_basic)
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
Date :: 2024-09-10 10:44