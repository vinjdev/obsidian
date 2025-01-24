24/11/24 14:23
Fag: [[IDATG2202]]
Tags: [[NTNU]]
___
# IDATG2202 - eksamen KX23

## 2
![[Pasted image 20241124142421.png]]

a read from memory
no more need for cpu

## 3
*local variables*

## 4
transistion into the operating system kernal at the request of the user program

## 5
kernal has full and direct access to machine hardware

it has urestricted access to acccess to hardware.
can control cpu and IO devices

## 6
First wait() for the return of fork() to spawn a new process, and then exec() to replace the
executable code
this is wrong

First fork() a new process, then exec() to replace the executable code, and then wait() for
the child process to terminate

alltid forke først

## 8
pthread join
venter på den ene er ferdig


## 10
That a process waits in a while loop until an event (typically a spinlock that changes value)
occurs.

## 11 - dma
what is direct memory access

where hardware I/O devices transfer data to and from main memory without continuous
involvement of the CPU

## 12
The file system is protected if a power outage happens

## 14
parent directory

## 15
it lets you run a program as someone else

## 16

## 17
pushq
move rsp rbp
movl 0

## 18
l1 cache is the fastest

## 19
6 minutter å kjøre en prosess
6 minutter tar det

## 20
by splitting up the prcesses in time slices, happens so fast it appears to run at the same time

by giving each process its own address space which OS devides into pages and maps them to the actual physical memory

making a abstraction of the file. here data here is stored on the disk and is maped by metadata so OS can fetch back the correct data

## 21
```c
int main() {

	pid_t rc = fork();
	if (rc == 0) {
		printf("my pid is %d",getpid());
		exec("/bin/date"); 
	}

}
```


## 22
1. rule one priority A > pri B. A runs b doesnt
2. pri A == pri B. Round robin those two
3. new job is placed in highest queue. (short response)
4. job takes up a TIME SLICE. pri is reduced
5. if job gives up CPU (becouse of IO) it stays

its a fair alogrithm which prioriteze short runnning jobs and high response time, solves shortest job forst without causeing startvation
- startvation is when one job runs for too long
- since cant predict how long a job would take

## 23
1. 20 000 000 - første skal bli 0 andre skal gjøre det til 20 mill
2. there is no locks on the operations with global values
3. locks around global operations


## 24

size of bitmap
= memory / page size

1gb = 2³⁰
2³⁵ / 2¹² -> 2²³ (number of pages)

2²³ / 2³ -> 2²⁰
*1mb*

## 25
container is an enviroemnt which runs a specific set of instructions in a closed enviroment inside a host OS using the host hardware


conatiner is a set of processes
- isolated through namespaceing
- reource limited
- limited in filesystem

it shares the OS



# Referanse
