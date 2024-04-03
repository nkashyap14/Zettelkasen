# Compiler

- Takes source code, reads it, generates [[Machine Code]] instructions and then saves them on a disk drive
- Does not handle execution of the resulting [[Computer Program]]
- Compilation Process:
	- Compiler handles first step of taking source code and reading it and creating an intermediate object file
	- Second step involves linking where the [[Linker]] comes in
	- Linker uses the intermediate object files to create an [[executable file]]
	- Reason these are kept separate is due to [[RAM]] size and dependencies
	- It is simpler for the [[Linker]] to track dependencies in the intermediate machine code otherwise in a combined service it would require extra passes through the whole program source code to resolve dependencies
---
Topics :: [[Computer Science]] [[Programming Languages]] [[C]] 
Reference ::
Type :: #atom
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2024-04-01 12:51
