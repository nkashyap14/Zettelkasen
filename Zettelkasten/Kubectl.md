# Kubectl

- Kubernetes [[Command Line Interface]] 
- Used in 2 ways
	- [[Declarative]]
		- Create manifest files that define what we want and send them to the cluster 
		- Better for production
	- [[Imperative]]
		- Give cluster specific orders on what we want 
		- Better for dev + test
- Commands:
	- Kubectl describe
		- gives us a detailed view of the object we are describing
	- kubectl get
		- gets information about specified resource 
		- kubectl get -o wide nodes 
	- kubectl top nodes
		- Gets nodes which are consuming the most resources
	- kubectl top pods --all-namespaces
		- gets total pod consumption in all namepsaces
	- kubectl top
		- shows memory and cpu consumption at the point inn time when command is run

---
Topics :: [[Kubernetes]] [[System Design]] [[Computer Science]]
Reference ::
Type :: #atom
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2024-04-01 10:21
