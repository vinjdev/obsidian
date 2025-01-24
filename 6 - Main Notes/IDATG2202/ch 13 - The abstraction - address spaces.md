24/09/24 11:05
Fag: [[IDATG2202]]
Tags: [[NTNU]]
___

# ch 13 - The abstraction - address spaces

Early days pc not expected to do much

## Early systems
OS just a set of routines(library). one process ran at the time

## multiprogramming and time sharing

[[ch 4 - Abstraction the process]] - time sharing

more expensive machine gave birth to multiprogramming. Multiple processes

time sharing started with running one proccess, giving full access to all memory.load some other process state. To slow as memory grew

![[Pasted image 20240924111355.png]]
a,b,c each have a small part of memory. OS chooses which process to run. important to protect, dont want process to read or write some other process memory

the example over shows how a process gets full access to all memory. really inefficiant.


## address space
address space = *abstraction* of the physical memory

![[Pasted image 20240924111719.png]]
stack and heap, implemented

in the top we place the code. where *instructions* reside.

heap is for user requested memory allocation

stack is for having local variables and pass parameters and function calls - automaticly managed

put them opposite, as the grow towards each other.

as we virtualize we need to handle where it is stored. if we wanna store some data in memory in address 0, which is not going there. But at some other place. WHICH THE VIRTUALIZATION SOULD HANDLE


## Goal
with virtual memory we want 
- *transparency* stays invisble for running program
- *efficency* in terms of time
- *Protection* - should not affect other memory content when os performce something on the memory - should be isolation



when printing out a pointer in C. we see the virtual address



# Referanse
