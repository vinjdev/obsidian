16/09/24 17:15
Fag: [[IDATG2202]]
Tags: [[NTNU]]
___

# ch 7 - Scheduling Introduction

os defines some scheduling policies so we have a order of operations

## workload assumptions
need to know ABOUT the workload
will makes assumptions about process
![[Pasted image 20240917134602.png]]
this does ofc *not* happen

## scheduling metrics
*turnaround time* - *time job completes* minus the time of *arrival*
![[Pasted image 20240917134814.png]]
only care about when the job is done
the average turnaround time, takes the whole process into consideration.

en slags tid som sier noe om *hvor lenge en process må vente*(fra den kom)


### first in first out
simple algorithm for schedulin processes
![[Pasted image 20240917135028.png]]

average turnaround time is
10 + 20 + 30 = 60 / 3 = 20

*convoy effect*
![[Pasted image 20240917135521.png]]
![[Pasted image 20240917135615.png]]

this whole process waits for A to finish. and as B and C cant start before a is finshed
other way around would be like this

10 + 20 + 120 = 150 / 3 = 50
alot faster

## Principle of Shortest Job first(SJF)
![[Pasted image 20240917135725.png]]

![[Pasted image 20240917135758.png]]

should always incoorporate shortest job first


Problem now - jobs do not arrive at the same time
SJF - only works if jobs come at SAME time
![[Pasted image 20240917140250.png]]
still get same problem EVEN with sjf used
![[Pasted image 20240917140331.png]]
= 103
(turnaround bryr seg om når de kom, derfor den er litt raskere enn uten sjf)

## Shortest time to completion first (STCF)
sjf is non preemptive scheduler
![[Pasted image 20240917140839.png]]


when a new job enter, it will be determined who has the *least time left*
only good if sjf is there

new metric:
*Response time* - ![[Pasted image 20240917141030.png]]
the example above
A = 0, b = 0 and c = 10, = *3,33 avrage*
c waits for b

this is good for turnaround time, bad for response

## Round robin - good for response itme
![[Pasted image 20240917141315.png]]

runs jobs for a *time slice*
(schedule quantum)
average response RR time here = 0+1+2 = 3 / 3 = *1*

average response SJF time here = 0+5+10 = 15 / 3 = *5*

the cost of *context switching* will dominate overall performance

RR is also really bad for turnaround metric

## Incorporation I/O

assumption nr 3 - with IO
an interrupt should be able to take place

## Is not known
do not know the length of a job, so how to incoorporate





# Referanse
