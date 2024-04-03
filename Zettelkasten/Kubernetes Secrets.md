# Kubernetes Secrets

- While [[Kubernetes Configmap]] is used to store configuration parameters secrets are used to store sensitive bits of information
- Secrets are stored in base64-encoded format
	- Obfuscated but not secure as anyone can decode
- Types of secrets:
	- Opaque secrets
		- Arbitrary user defined secret
		- Can create from file, yaml, json, or cli
	- Service Account tokens:
		- Used for built in cluster rbac by pods
	- Docker config secrets
	- Basic Auth secrets: Auth info
	- SSH auth secrets
	- TLS certs
- Recommended to do secrets as file mounts and not environmental variables as they are treated securely by kubernetes but not by container rutntime so container runtime may decode the secrets and log them

---
Topics :: [[Computer Science]] [[Kubernetes]]
Reference ::
Type :: #atom
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2024-04-01 11:55
