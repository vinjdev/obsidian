29/08/24 15:53
Fag: [[IDATG2202]]
Tags: [[NTNU]] [[OS in three pieces]]
___

# Abstraction the process
*How can we run more than one program at onece?*

Os creates a illusion called *Virtualization*
- runs one process, stops it, and runs another one
	-time sharing

the more programs the slower performance (takes longer time to run)

OS is some policies (alogrithms) that makes decisions for the OS.
*scheduling policy*, what should run?

program is lifeless - just lives on the disk

OS handles process on program

few physical CPUs available - need to utilize this

*time sharing* - man process start and stop really fast
*context switch* - stop one start another

## abstraction: a process
process = running program


*machine state*
- memory = contains instructions
- address space
- registers also contains instructions
- instruction pointer(IP) - register for which instructions is being ran

stack pointer and frame pointer used to manage local variables, function parameters and return addresses


# process API
an OS should..
- create - OS should create a new process
- destroy - shut down process
- wait - wait for a process to stop running
- miscellaneous control - suspends a process
- status - get information about a process

![[Pasted image 20240903142517.png]]

# Process creation
how does an OS get a program up and running?

load code and static data onto memory
OS read from a disk to place them into memory

OS does this LAZY. takes only what it needs

Most *allocate memory* for programs runtime STACK
stack needed for local variables and function parameters
OS allocates this and give it to the process.

THEN allocate for programs HEAP. dynamically allocated memory
this data small at first, and will build up under run time

then inits I/O  for input and output. then program starts it execution.

# process states
A process is either 3 states:
*running* - executing instructions
*Ready* - OS chose not to run the process
*Blocked* - process has done something that stop it until some other event happens. 
![[Pasted image 20240903144442.png]]


# data structures
a *process list* to track the state of each process

OS need to have control over what is running, blocked and ready




write policy
write through - write to cache line and back to memory
write back - write to cache line and mark cache line as dirty



# Referanse
kap 4. i boka