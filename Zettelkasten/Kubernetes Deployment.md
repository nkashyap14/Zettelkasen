# Kubernetes Deployment

- A deployment allows us to create multiple [[Kubernetes Pod]] from the same [[YAML]] definition file and to easily perform updates on deployed pods 
- Under the hood:
	- Deployment creates a [[ReplicaSet]]
	- ReplicaSet creates replica pods 
		-ReplicaSet maintains a stable set of replica pods running at any given time
- Used to define the desired state of an application
- When deploying pods we set [[CPU]]/[[Memory]] limits under requests
	- If CPU limit is hit we get throttled
	- If memory limit is hit we get restarted
- Selector sectionn in the declarative manifest [[YAML]] is what tells kubernetes which deployments the pod is monitoring
- Deployments run the [[Kubernetes Reconciliation Loop]]
- Adding pods to a deployment is adding additional [[compute]] power to the deployed application
---
Topics :: [[Kubernetes]] [[Computer Science]]
Reference ::
Type :: #atom
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2024-04-01 10:07
