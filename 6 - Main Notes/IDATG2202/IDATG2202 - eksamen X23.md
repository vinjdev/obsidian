24/11/24 19:48
Fag: [[IDATG2202]]
Tags: [[NTNU]]
___
# IDATG2202 - eksamen X23

flervalg på blackboard:
64kb -> 2¹⁶
offset = 16 bits
vpn er jo alltid det siste 8 binare tallen i addressen der page addressene er



## 4
eip / rip
stores the next instruction
![[Pasted image 20241125085337.png]]

## 5

$4

## 6
response time

## 7
RR

## 8
text/code, data, heap, stack

## 9
text/code is ofc shared
data/heap is also shared along same process
and files will also be shared in the same process

## 10
cond wait. will asssume that the mutex is locked

## 12
its distributed across all the disks

## 13
/ -> temp -> a.dat
need to check the i node number and the superblock first

## 15
isolated and protected on the system call interface

## 18
4 cores
3 minutes
6 processes

3 mins
2 processes

*= 4.5 mins*

## 19


001000000000010
100 0000000010

*det er akkurat det samme*



## 20
directory entry is
file name and inode number

## 22
use ls * .c | wc -l

find . -type f | fgrep "basicLock.c"
use this to find specific file

## 23

```c
int main() {

	pid_t rc = fork();
	if (rc == 0) {
		int local = 20;
		printf("value: %d is in %p\n",local,(void*)&local);
		exit(0);
	}
	else {
		waitpid(rc,NULL,0);
		printf("child done\n");
		return 0;
	}
	
}
```


## 24
in random oreder 3! = 6
bare husj at sem_wait wil stopp de andre. og sem post vil starte den igjen

## 25
need to be some restricted operations for the program where it could perform io

## 26
3 processes
6 + 12 + 18 -> 36/3  -> 12

0 + 4 + 8 -> 4

## 27

2³⁰ = 1gb
2³⁸ / 2²¹-> 2¹⁷

2¹⁸ / 2³ => 2¹⁴ 16kb

## 28
tlb is a a small and fast cache inside the mmu which handles the address translation for the mmu so the cpu can quicklyfetch memory from ram

it will be a cache miss whenever a new page is accessed

## 29
gets does not check the length of the buffer 

can do buffer overflow. meaning a potential attack could take control over the execution




# Referanse
