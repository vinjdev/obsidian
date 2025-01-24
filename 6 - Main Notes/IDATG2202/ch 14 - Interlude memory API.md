19/09/24 17:07
Fag: [[IDATG2202]]
Tags: [[NTNU]]
___

# ch 14 - Interlude memory API
How to allocate memory in a robust and relaiable way

## types of memory
stack are memory type allocated *implicity* by COMPILER

Heap is where allocation and deallocation is managed *explicitly* my PROGRAMMER

![[Pasted image 20240919171352.png]]
this allocates memory for a pointer to an interger on the heap

## the malloc() call
malloc ask for some space on the heap
if not succed return NULL pointer

if succeded, then give up some space based on requested size.
using the sizeof operator

## free()
always free up the memory

## Common errors
Today we have garbage collectors that handle memory managment

![[Pasted image 20240926204255.png]]
forgetting to allocate memory. Here dst need to have allocated some space, as its just a pointer to a address somewhere. 

Forgetting to initialize allocated memory. also bad.

### memory leak
leads to run out of memory
when done with a chunk of memory then free.

but for a program with SHORT RUN TIME (it exits after 1 sec). No point, as OS handles the clean up.

## Other calls

Calloc useful to have a initialzed pointer. which means there is a value stored inside JUST 0
```c
arr = (int*) calloc(4,sizeof(int));
```
this makes a array of 4 ints containig the value *0 in all indexes*

# Referanse
