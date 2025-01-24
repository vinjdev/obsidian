23/11/24 15:04
Fag: [[IDATG2202]]
Tags: [[NTNU]]
___
# IDATG2202 - eksamen nov 2022

# flervalg

## 1
![[Pasted image 20241123150454.png]]
2

## 2
![[Pasted image 20241123150515.png]]

![[Pasted image 20241123151157.png]]

## 3
![[Pasted image 20241123152929.png]]

![[Pasted image 20241123153010.png]]

## 4
![[Pasted image 20241123153149.png]]

![[Pasted image 20241123153157.png]]
- affect how hardware responds to IO devices

## 5
![[Pasted image 20241123153609.png]]

![[Pasted image 20241123162252.png]]
- enabled using context switching
- switching rapidly between processes

## 6
![[Pasted image 20241123162725.png]]

![[Pasted image 20241123162755.png]]

## 7
![[Pasted image 20241123165528.png]]

![[Pasted image 20241123170523.png]]

## 8
![[Pasted image 20241123170536.png]]

![[Pasted image 20241123170616.png]]

## 9
![[Pasted image 20241123171137.png]]

![[Pasted image 20241123171141.png]]

## 10
![[Pasted image 20241123171149.png]]

![[Pasted image 20241123171411.png]]
- tråder kan ikke kjøre uten en prosess, og den må ha memory, og den kjører ikke fortere

## 11
![[Pasted image 20241123171447.png]]

![[Pasted image 20241123171545.png]]

## 12
![[Pasted image 20241123171825.png]]

![[Pasted image 20241123172009.png]]
mov instructions that moves data between registers, and other parts of system

## 13
![[Pasted image 20241123172125.png]]

![[Pasted image 20241123172257.png]]

600 = rw- --- ---
inoder lagrer tilatelser bits, sammen med andre fil egenskaper

## 14
![[Pasted image 20241123175719.png]]

![[Pasted image 20241123175751.png]]

## 15
![[Pasted image 20241123180320.png]]

![[Pasted image 20241123181438.png]]

## 16
![[Pasted image 20241123181536.png]]

En prosess er bare *ready, running or blocked on IO*

## 17
![[Pasted image 20241123181832.png]]
movl
cmpl
jle

## 18
![[Pasted image 20241123205056.png]]

bruker alle 4 cores på 4 første prosesser
deretter tar siste prosess
den har 4 ledige cores. alle samarbeider
6/4 = 1.5
6+1.5 = *7.5 minutter*


## 19
P0 tar 25ms - io per 5 ms - io time tar 5ms
p1 38 - 15 - 5

![[Pasted image 20241123213329.png]]
![[Pasted image 20241123214611.png]]

turnaround = completion - arrival
response time = first starts running - arriavl

## 20
16 bit
offset = page size
offset = 2⁸
virtuell address space = 2¹⁶
page size = 2¹⁶ / 2⁸ => 2⁸
*page size = 256*

size of virtual address space is 2¹⁶ => 64kb

address space splitt into 
VPN 8 upper bits
offset 8 lower bits

upper = 14
lower = 

## 21

```c
int value = 20;

int main() {

	pid_t pid = fork();
	if (pid < 0) {
		printf("fork failed\n");
		return 1;
	}
	else if(pid == 0) {
		int stackValue = 11;
		printf("stack value: %p",(void*)&stackValue);
	}
	else {
		printf("value: %p",(void*)&value);
	}

	return 0;
}
```

```bash
gcc mysil.c -o mysil -Wall -Wextra
```

## 22
```c
int balance = 0;
pthread_mutex_t mutex = PHTREAD_MUTEX_INITIALIZER;
sem_t s;

void* worker(void* args) {
	pthread_mutex_lock(&mutex);
	balance++;
	printf("%s made balance: %d\n",(char*) arg,balance);
	pthread_mutex_unlock(&mutex);
	Sem_post(&s);
	return NULL;
}

int main(void) {
	pthread_t thread1;
	pthread_create(&thread,NULL,worker,(void*) "NewThread");

	Sem_wai(&s);
	worker((void*) "Mainthread");
	pthread_join(thread,NULL);
	
	return 0;
}
```


## 23
whats a freelist
freelist list of adresses to th each uits that are avaliable free

bitmap
keeps track of computer resources with bits. if bit is zero the space is avalibale

size is calcualtd

memory/page size

1 gb = 2³⁰
1 mb = 2²⁰
1 kb = 2¹⁰
2³⁶ / 2²¹ => 2¹⁵ (number of pages)

2¹⁵ / 2³ => 2¹² -> 4kb

freelist is the same just
2¹⁵ * 2⁸ -> 256kb

## 24
three things happens
1. overwrite the datablock, mark it as overwritlable
2. to delete a file on the ssd wipe the entire ssd. The ssd does wear leveling, so it distrubuting the writes over the entire ssd. 

## 25
user mode - application code runs natively on the cpu, no overhead
overhead is extra resources needed to perform some task

guest OS - the os inside a vm - cant control hardware, so hypervisor 

for each memeory access address translation involves two page table entries

MMU understands the two levels for page tables, so it maps both host and guest

## 26
discretionary access control
include three elements of access control entry: deny/allow, user/group, permission
allow admin fullcontroll








# Referanse
