17/09/24 14:31
Fag: [[IDATG2202]]
Tags: [[NTNU]]
___

# ch 8 - Scheduling MLFQ
MLFQ made to solve turnaround time with SJF - but we dont know length of job

MLFQ also want to solve response time with round robin (terrible at turnaround)

MLFQ - predicts the future

## BASIC RULES
queues with *priority*

more than one job can be on a *same queue*, so it *runs round robin*


![[Pasted image 20240917150443.png]]

if a and b is in priority. then something is left out
so priotrity needs to change

## How to change priority
![[Pasted image 20240917150727.png]]

if a job uses up a time slice, priority is reduced
job gives up before then keep th priority


MLFQ, will assume short job so i gives up priority - MLFQ is more SJF

## IO
rule 4b is for IO
dont want to penalize a job
so keep it at same level

## problems with current MLFQ
*starvation* - too many jobs wil take all CPU time


## the priority boost
after a time periode move all jobs in system to top priority



## summary
![[Pasted image 20240917154953.png]]
MLFQ observers execution and prioritze accordingly




# Referanse
