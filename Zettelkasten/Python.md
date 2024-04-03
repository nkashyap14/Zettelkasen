# Python

## Summary
- Python is a [[high level programming language | high-level]] [[interpreted language|interpreted]] programming language 
- Supports procedural, [[OOP]], and [[functional programming]]
- Is a versatile language thanks to its standard library + extensive ecosystem of third party packages. Very popular in [[Machine Learning]] and [[Data Science]]
## Subtopics
- [[Cpython]]
- [[Python Garbage Collector]]:
	- Main ideas for python:
		- maintains reference count
			- if count falls to zero job of collector is to deallocate memory associated with the variable
		- periodically determines reference cycles
			- if a refers to b and b refers to a means reference counts will never hit 0
			- collector determines and resolves this
		- Performance enhanced with heuristics
			- Objects that are created more recently are more likely to be garbage collected
			- Uses the concept of generations to handle this
	- Under the hood memory that is freed up by python's garbage collector isn't freed up for the system. Python continues to occupy that memory and reuses it as it sees fit
- [[Python Reference Cycle Detection]]
- [[Software Design Patterns]]
- [[Python threading library|threading]]
- [[Python multiprocessing library|multiprocessing]]
- [[Python lambda's|lambdas]]
## Code in Execution

- [[Binary Tree Check for Identical Python Code|Binary Tree Identical]]

## Details
- Execution of any python [[Machine Code|bytecode]] requires possession of the [[Global Interpreter Lock|GIL]].
- Uses [[reference counters]] for memory management
	- Reference counters keep track of the amount of references that point to an object
- In python it is better to be [[multiproccessing|multiprocesssed]] instead of [[multithreading|multithreaded]] for parallel execution as each python process gets its own python interprete, memory space, and gil which allows for true [[Concurrency]]
- When a python program is executed a global scope is created
	- Each variable in that scope is global
	- each [[object]], [[function]], [[method]], [[loop]], [[ifs statement]], [[try catch]] block starts a new scope
	- new scope has access to all variables defined in enclosing scope
	- when a program reaches the end of a scope it closes all variables  in that scope
- pymalloc allocates memory in 256 kb chunks called arenas. The areans are then divided into 4kb pools which are in turn subdivided into fixed size blocks 

## Conclusion


Type :: #topic
Links :: [[Computer Science]] [[Programming Language]]
Creator ::
Date ::  2024-04-02 22:07