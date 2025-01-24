25/11/24 12:09
Fag: [[IDATG2202]]
Tags: [[NTNU]]
___
# IDATG2202 - eksamen KX24

## 3
a read from memory has finished

## 4
base pointer points to local variables

## 5
when io

## 6
convoy effect is when a big process takes up to much processing time
meaning it would take longer for other to response

*first in first served *


## 7
*shortest time to completition* would always be the best for turnaround time

## 8
its race conditions since we dont know which thread would be executed first

## 12
hard links are limited to same filesystem
symbolic links can be any other place within

## 13
hypervisor was introduced

## 14
all interupts goes directly to the guest operating system

## 15
they want to keep the desing as simple and small as possible

## 16
privileges is the thing which is present in access controll

## 17
it shoould be 0

## 18
pages

## 19

applikasjon gjør commandoer
OS gjør system call
assembly gjør instruksjoner

## 20

fører til eksonensiell vekst av prosesser
ettersom det vil forkes videre og videre

## 22

```c
int main() {

	pid_t rc = fork();
	if (rc == 0) {
		print("mysil\n");
	}
	else {
		waitpid(rc,NULL,0);
		print("solan\n");
	}

	return 0;
}
```

```bash
gcc kjell.c -o kjell -Wall
```


## 23
512 = 2⁹ -> 9 bit offset

110 er vpn

101 så den fysiske addressen blir

1011 1011 1010

present bit er der så det blir ikke page fault

## 24
kan bli 6,7 eller 8
trådene overskriver hverandre, som betyr at alt mulig kan bli slutt resultat av disse 3

## 25
what is the problem
når man låser mutex før man gjør en down på full eller empty

kan blokkere en process på en down, så det blir en deadlock

## 26
store blokker samler mer på ett sted. da raskere å lese
store blokker kan gi intern fargmentering siden større mengder ddata i allokerte blokker som ikke blir brukt

for små blokker blir tregere, og fører til mer metadata, som tar mer plass

## 27

kan være endringer mellom disse to funksjon callene





# Referanse
