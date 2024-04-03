# Interpreter

- Reads source code in parts, generates [[Machine Code]] and executes them immediately
- Stores intermediate results in the [[RAM]]
- Interpreters are slower than machine code executions because every time you execute the program via the interpreter it requires a translation from source code to [[Machine Code]]
	- Also slowed down due to [[disk I/O]]. Source code needs to be loaded from disk drive into the [[RAM]] which can cause the [[CPU]] to idle as data gets loaded
- Interpreter by itself is a complex program that requires a portion of the computer's [[hardware]] resources to launch and execute. The computer has to execute the interpreter in parallel with the [[Computer program]] and share resources between them. This is extra overhead
---
Topics :: [[Computer Science]] [[Compiler]] [[Machine Code]]
Reference ::
Type :: #atom
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2024-04-01 14:58
