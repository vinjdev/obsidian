30/09/24 14:20
Fag: [[IDATG2202]]
Tags: [[NTNU]]
___

# ch 19 - Paging Faster Translation
Needs extra memory for mapping all the location for the pages
Need to speed up the translation

TLB solves this - buffer
part of the CPU Cache - MMU memory managment unit
- cache = address-translation cache

accesing memory is SLOW - so we use MMU for this
Almost all speed problems with *caching or paralization*
## TLB Basic algorithm
it a algrothm that cheks for TLB holdes the translation for the VPN it needs
can then extract the *page frame number*

This happens in *MMU* - so TLP is a buffer (buffer = cache)


## example accessing an array
![[Pasted image 20240930143643.png]]
here a start in vpn 6 on offset 4

in a simple for loop. the program will constantly look for tlb hits for where a[] is locaated in memory with the page table

![[Pasted image 20241001101054.png]]

temporal locality would make it QUICKER the SECOND time
temporal locality = recently accesed
spatial locality = if program access x then the next "x" would be near

![[Pasted image 20241001140833.png]]
unngår alltid å sjekke page table. fordi page table er tregt

tar pagenr sjekker om den er i MMU (TLB). får en hit å finne den fysiske addressen basert på dette.

## who handles the TLB miss
before hardware handle TLB miss
now on tlb miss hardware raise an execption, and raises privilage

## TLB contents whats in there
TLB entry looks like:
![[Pasted image 20241001103254.png]]
VPN = virtual page number
PFN = page frame number
There are different types of bits which would incluence the action

## TLB issue context switches
switching between processes (and addresses) would raise a issue.

![[Pasted image 20241001104027.png]]
VPN 10 translate PFN 100 or PFN 170
Which one should i choose?

one solution - FLUSH the tlb on switch (so its empty)
can be costly

![[Pasted image 20241001141917.png]]

another solution - add ASID (like a process identifier) 
- it marks which process this line belongs to 
- we know dont need to emppty the cache


hvis vi skifter for ofte mellom prosesser "rekker" ikke caching å skje

hvis MMU har cache fysisk addresse
finner med en gang
TLB Miss = page table walk


## Issue replacement policy
cache replacement is a isssue
need to install a new one, when getting a entry in the tlb


# summary
hardware makes translation faster (caching)

if number of pages acceses exceed number of pages fits into TLB, then alot of misses. therefor adding a support page.


# Referanse
