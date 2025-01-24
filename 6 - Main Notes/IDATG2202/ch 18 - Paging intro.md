26/09/24 21:11
Fag: [[IDATG2202]]
Tags: [[NTNU]]
___

# ch 18 - Paging intro
segmenation - divided physical memory onto segements or blocks
- conisit of code(text), heap and stack
- Pure segmentaion Not standard today
- they are flexible as they grow in size. allows for multiple process to segemenets
- problem with *fragmentation* with free spaces.
How to virtulize memory without segments.

example of why segmentation is bad:
- system with 100 mb
- allocated 10,20 and 30 mb
- free the 20 MB
- now its a gap between -> now if something as big as 25 it cant be allocated. would need a multiple non contiguous spaces.



paging split up in fixed sized units called a page

![[Pasted image 20240927085626.png]]
this is a tiny address space. 64 bits in size. 16 per page

call each a page frame first is 0
no longer need a asumption of how heap and stack grow

to record each virtual page - has PAGE TABLE (stores address translation)

![[Pasted image 20240927093242.png]]

to perform address translation with a virtual address
We need the VIRTUAL PAGE NUMBER (VPN) and OFFSET

# Where are page tables stored
page tables can get big. 
and need space just for address translation. just store the page table of each process in memory somewhere

# whats actually in the page table
datastructure map virtual addresses
linear page table - simplest

protection bits - indicate page can be read from

present bit - indicate if page in is physical memory or swaped out

dirty bit - has been modified

reference bit - has been accesed?

# paging also too slow
![[Pasted image 20240927094415.png]]
here need to trnslate virtual address for 21 into correct physical address. before loading to address for 21. it need to fetch the proper *page table entry* 

hardware must know about the page table location.
*page table base register*.

![[Pasted image 20240927095046.png]]

# memory trace

# Summary 
paging better than segmenation

no external fragmentation
flexible

slower - extra memory accesses to access page table
memory waste- filling memory with page tables

could be useful applicaiton data instead




# Referanse
