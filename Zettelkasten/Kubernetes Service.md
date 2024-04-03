# Kubernetes Service

 - Network level abstraction. Allows us to expose multiple [[Kubernetes Pod]] under a single IP and single dns name
 - -Each pod has its own private ip which shouldn't be relied on as it can change at any point
 - Types of Services:
	 - Type ClusterIP:
		 - Exposed on an IP that is reachable from only inside the cluster
	 - Type NodePort:
		 - Accessible from outside the cluster by connecting to the IP of a node and the specified port 
		 - Opens a port on all the worker nodes in the cluster and redirects requests received on that port to the correct location
		 - Builds ontop of cluster ip, everything cluster IP can do so can NodePort
	 - Type LoadBalancer:
		 - Azure/Cloud load balancer that gets a public IP that can be used to connect to 
---
Topics :: [[Kubernetes]] [[Computer Science]]
Reference ::
Type :: #atom
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2024-04-01 10:08
