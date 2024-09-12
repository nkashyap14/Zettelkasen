# Azure Machine Learning CLI extension

- Commonly used by administrators and engineers to automate tasks in Azure
- Allows us to automate creation and configuration of assets and resources to maek it repeatable
- Ensure consistency for assetsw and resources that are replicated in multiple environments
- Integrate into [[Devops]] workflows like [[Continuous Integration and Continuous Deployment (CI/CD)]] pipelines

```
az extension add -n ml -y #install extension

az ml -h #help command
```

```
az ml compute create --name aml-cluster --size STANDARD_DS3_v2 --min-instances 0 --max-instances 5 --type AmlCompute --resource-group my-resource-group --workspace-name my-workspace #create a compute resource
```


- Can also define the configuration in a [[YAML]] file and then use that file as to create
```
$schema: https://azuremlschemas.azureedge.net/latest/amlCompute.schema.json 
name: aml-cluster
type: amlcompute
size: STANDARD_DS3_v2
min_instances: 0
max_instances: 5
```

```
az ml compute create --file compute.yml --resource-group my-resource-group --workspace-name my-workspace
```
---
Links :: [[#Example Code]] [[Computer Science]] [[DP-100]] [[Azure]]
Reference ::
Type :: #code
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2024-09-10 13:03
