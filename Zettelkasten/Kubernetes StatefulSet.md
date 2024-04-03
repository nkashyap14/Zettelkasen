# Kubernetes StatefulSet

- Used to handle stateful workloads
- Is a [[Kubernetes Deployment]] with the additional capability of ordering and uniqueness of [[Kubernetes Pod]]
- Ensures that pod and its storage are kept together
- Also maintains a sticky identity for each of its pods, aka pods are not interchangeable and each has a persistent identifier
- When a pod is deleted it is relaunched on the same node it was running on

---
Topics :: [[Kubernetes]] [[Computer Science]] [[System Design]]
Reference ::
Type :: #atom
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2024-04-01 10:25
