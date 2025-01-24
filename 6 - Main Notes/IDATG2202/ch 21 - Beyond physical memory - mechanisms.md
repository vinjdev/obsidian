04/10/24 09:10
Fag: [[IDATG2102]]
Tags: [[NTNU]]
___

# ch 21 - Beyond physical memory - mechanisms
address space is REALLY BIG in 64 bits
we need to go beyond physical memory

running multiple processes at once
pc cant hold all the pages at once. 

## swap space
reserved space on disk to use for memory

## The present bit
if VPN in not found through tlb. then page table walk
present bit is eiterh 0 or 1 (on memory physically or on disk)
IF not in memory then page fault.

## page fault
when page fault. let page-fault handler determine what to do

TLB trusts this.

when fault happens, checks page table entry find address and fetch page into memory

## what if memory is full
need to page out to make space. wrong call here can cost performance

## page fault control flow
TLB decides if page walk is necceary
if no hit. then check pfn from pte. retry instruction tlb hit
if no hit and no present bit. then page fault handler do it job. so it can retry process

this retry wil result to a tlb miss, and the second try will work



# Referanse
