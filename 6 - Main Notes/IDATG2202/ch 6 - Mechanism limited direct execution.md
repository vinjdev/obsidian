09/09/24 13:26
Fag: [[IDATG2202]]
Tags: [[NTNU]]
___

# Mechanism limited direct execution

cpu need to share physcial cpu for [[Virtualization]]

*time sharing* - run a process abit, then another

OS must have CONTROL - to be able to stop and start processes

## Basic technique: limited direct execution
direct executing is just run the program on the cpu

when OS want to run a program, makes a process entry in process list
allocates memory, load code into memory

![[Pasted image 20240909142143.png]]

basic direct execution

this NOT good for virtulization
Cant do time sharing now. (stop process and run another one)
- for virtulization

## Problem 1 - restrict operations
direct execution is fast
but restricted operation like accesning the disk. is not possible

how can OS and hardware work together. need to be control over system

USER mode - application do not have access to all instructions
KERNAL mode - full control

*System Call* = user Mode can access kernal instructions
- program executes a trap instruction (raises priviligium)
- then a return-from-trap

*trap table* - OS need to know what traps is good to go for control

## problem 2 switching between processes
how can OS decide to stop a process and start another one??

OS waits for control over cpu when an illegal operation takes place







# review
1. to provide the user with an api and have control over the hardware / system resources. 
2. synchronous interrupts happens as a direct result of program. are predictible
	asynchronous - happens independently of programs execution and is not predictable




# Referanse
