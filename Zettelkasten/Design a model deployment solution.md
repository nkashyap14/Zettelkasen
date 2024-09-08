# Design a model deployment solution

## General Details

- Can deploy models to endpoints
- Two options
	- Real-time Predictions from an endpoint
	- Batch Predictions from an endpoint
		- Want model to score new data in batches and then save the results to some storage
- Choosing between the two above requires a few considerations
	- How often should predictions be generated
	- How soon are results needed
	- Should predictions be generated individually or in batches
	- How much compute is needed to execute the model
	- Does not depend on the frequency of data collection
- Compute:
	- With real time predictions requires compute that is always available and able to return the results immeidatley
		- Might require container technologies like [[Azure Container Instance (ACI)]] or [[Azure Kubernetes Service (AKS)]]
	- Compute is always on, constant cost
	- With batch predictions requires a compute that can handle a large workload
		- Compute cluster that can score data in parallel batches
		- Compute is provisioned when the batch scoring is triggered and 0 nodes when there is no new data to process
		- Can lead to savings as efficient compute utilization occurs
		- May lead to delay as compute scales up
## Subsections

## Terms defined

- [[Endpoint]]

Type :: #topic
Links :: [[DP-100]] [[Azure]]
Book :: 
Date ::  2024-09-08 07:47