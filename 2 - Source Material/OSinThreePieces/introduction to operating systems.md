22/08/24 13:42
Fag: [[IDATG2202]]
Tags: [[NTNU]] [[OS in three pieces]]
___

# intro os in three pieces
program executes instructions
fetches from memory and decodes it and executes it

*make a system easy to use*

The layer between software and device (the OS)

Virtualization
takes physical resource (processor or memory)
makes a more powerful version of it self as a *virtual* form

OS proivde a *API*, something to make it easier to handle

virtualization makes it so more programs can share the same resource
*resource manager* os task is to manage resoureces of the system

## virtualizing the CPU

![[Pasted image 20240822135256.png]]
program som kaller spin() som sjekker tiden mange ganger
Dette programmet kan kjøre flere ganger på en gang.
![[Pasted image 20240822135439.png]]
tar inn en argv så man kan sende inn flere å de vil kjøre samtidig. Enkel demostrasjon av virtualisering

What should be able to run is decided by the *resource manager*
- an api that makes it possible to communicate to the os what programs needs to be used.

## Virtualizing the memory
memory = array of bytes
fast access, program is using memory at all time

same with the cpu we can assign multiple instance of memory with the same address, as if they ran independently

## Concurrency
host of promblems that need to be addressed, when working on many things at once

Os is juggling many things at once, can lead to deep problems

some functions will handle different things and wont run atomically (all at once), therefore it wont have chance to execute the program in time

## Persistence
in system memory data can be lost. DRAM, will store this data , when something unexpected happens(power goes off, or something)

SSD and hard drives. Common repositories for storing long lived information (games and data etc).


# Referanse
