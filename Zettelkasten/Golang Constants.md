# Golang Constants

## Definition:

- Value that can't be changed by the program
- Defined using keyword const
```
const identifier [type] = value
//identifier being the name and type being the type of the constant

//[type] is optional because the compiler can implicitly derive the type from the value
const PI = 3.1459
const b = "Hello"
const B string = "hello"
```

- [[Typed Constants]]
	- Decalred through explicit typing
- [[Untyped Constants]]
	- Declared through implicit typing
	- Becomes typed when it is used within a context that requires a typed value
- Must be evaluated at comiple time
	- Can be a calculation but values necessary for calculation must be available at compile time
- No size or sign. Can be of arbitrarily high precision and do not overflow
- [[Golang Enumerations]]
---
Links ::  [[Golang]] [[Computer Science]] 
Reference ::  
Type :: #definition
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2024-10-07 06:32