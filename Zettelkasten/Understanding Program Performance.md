# Understanding Program Performance

## Definition:

| Hardware or software component   | Affects what?                                                                   | How?                                                                                                                                                                                                                                                        |
| -------------------------------- | ------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [[Zettelkasten/Algorithm]]                    | [[Instruction Count]] and possibly [[Clock Cycles Per Instruction (CPI)]]       | Determines number of source program instructions generated and executed and thus number of processor instructions executed. May favor faster or slower instructions. Ie if it favors more divides than it will lead to a higher CPI                         |
| [[Zettelkasten/Programming Language]]         | [[Instruction Count]] and [[Clock Cycles Per Instruction (CPI)]]                | Statements in language are translated to processor instructions which determine instruction count. May affect CPI because of its features, ie a language with heavy support for data abstraction like [[Java]] will require indirect calls which raises CPI |
| [[Compiler]]                     | [[Instruction Count]] and [[Clock Cycles Per Instruction (CPI)]]                | Efficiency of the compiler affects both since compiler determines the translation of the source language instructions into computer instructions                                                                                                            |
| [[Instruction Set Architecture]] | [[Instruction Count]] and [[Clock Cycles Per Instruction (CPI)]] [[clock rate]] | Affects instructions needed for a function, cost in cycles of each instruction, and the overall clock rate of the processor which is a clock cycle divided by seconds. Aka how many clock cycles fit into one second.                                       |


---
Links :: [[Computer Science]]
Reference ::  [[Computer Organization and Design MIPS Edition]]
Type :: #atom
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2024-09-18 09:05
