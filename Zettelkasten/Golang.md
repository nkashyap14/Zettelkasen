# Golang

## General Details

- Belongs to [[C]] family
- Package model:
	- clean dependency analysis and fast compilation
	- All of the go standard library compiles in less than 20 seconds
	- Negligible compilation times
	- Execution speed of native code is comparable to C
- No concepts of classes
- Code is structured as statements that don't have to end with a ; however the compiler auto inserts the ; at the end
	- Multiple statements on one line will need to be separate with a ;
- Each go file belongs to one package
	- Package must be indicated on line one
- Each go app has one main
- When a variable is declared memory in go is initialized
	- Contains the default value zero or nil  automatically
	- or false for bool
- Go-compiler is intelligent enough to derive the type of a variable from its value dynamically, also called _automatic type inference_ at runtime, so omitting the type of a variable is also a correct syntax
- Short form assignment with := operator can only be used inside functions not in package scope
	- Makes a new variable
	- Called an initializing declaration
- Memory in a language is used in denominations of [[word]]
- Variables of elementary type like int, bool, float, string, are value types
	- They point directly to their value in memory
	- Contained in [[stack memory]]
- Complex data types which need several words are treated as reference types
	- A reference type variable contains the address of the memory location where the value of variable is stored
	- This address is called a pointer
	- The values referenced are usually stored in the [[heap memory]] which is usually garbage collected and has a larger memory space than the stack
- Go has architecture dependent types like int, uint and uintptr which take the appropriate length based on the architecture of the machine its running on
- byte type is an alias for uint8
- characters are a special case of integers
	- var ch byte = 'A'
- / is floored division
	- 9 / 10 gives 0
	- 9 / 2 = 4
- No error generated when overflow occurs because high bits are simply discarded
- 
## Features

- [[Statically Typed]]
- [[Compiler|Compiled]]
- Features of a [[dynamic language]]
- [[Inheritance via Interface]]
- [[Package definitions]]
- [[Polymorphism]] independent of inheritance like [[Javascript]], [[Ruby]], and other dynamic languages
- [[Imperative]] language
- Missing OOP features:
	- No function or operator overloading
	- No implicit conversions
	- No classes and type inheritance
	- No variant types
		- Implemented via interfaces
	- Dynamic code loading and dynamic libraries excluded
	- Exceptions not included
	- No assertions
	- No immutable variables
- Functional language
	- Functions as basic building blocks
- [[Strongly typed language]]
- [[Golang Data types]]
- [[Golang Constants]]

## Class References

## Code

- [[Basic Go Function]]


Type :: #topic #language
Links :: 
Book :: 
Date ::  2024-10-07 06:08