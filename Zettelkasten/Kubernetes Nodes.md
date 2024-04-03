# Kubernetes Nodes

- A typical cluster consists of a number of master nodes and a number of worker nodes
- Node is equivalent to a server or a VM
- Master nodes contain kubernetes API + DB that has cluster state 
	- Good practice to have more than one to maintain high [[Availability]]
	- Contains the API server which is the only part of the Kubernetes cluster directly interacted with
		- API server executes the commands that get sent to the server 
	- Contains the scheduler which chooses which nodes to run the user app on
	- Also has a Cloud controller allowing kubernetes to integrate with cloud services
- Worker nodes are the machines which execute the workload
	- Contains a kubelet which is the main kubernetes agent that joins the node to the cluster and communicates with the control plane 
	- Container runtime: Starts and stops runtime
---
Topics :: [[Kubernetes]] [[Computer Science]] [[System Design]]
Reference ::
Type :: #atom
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2024-04-01 10:10
