# Golang Enumerations
## Definition:

- List all elements of a set is called enumeration
```
const (
	UNKNOWN = 0
	FEMALE = 1
	MALE = 2
)

// iota used to enumerate, each call gives an incremented value, so 0, 1, 2
//iota gets initilazed back to 0 in a new const block of declaration
const (
	UNKNOWN = iota
	FEMALE = iota
	MALE = iota
)
```
---
Links ::  [[Golang]] [[Computer Science]] 
Reference ::  
Type :: #definition
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2024-10-07 06:37