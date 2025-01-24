29/08/24 17:03
Fag: [[IDATG2202]]
Tags: [[NTNU]]
___

# assembly explained

![[Pasted image 20240829170425.png]]


![[Pasted image 20240829170437.png]]

assembly dont need a variable, ONLY care about address in memory
løkker finnes heller ikke. man bare hopper fram og tilbake

long is 32 bits
4 byte
regular int for my pc

pushq is now on a 64 bit register onto stack
- register is on cpu sent to memory
this preserves it for when function returns

then movq value of a 64bit stack pointer into the 64 bit base pointer from before

then we move the value 0 ($ is a value). onto the -4(%rbp). setter den til å være -4 bytes from the base pointer

basiclly this
```c
int i = 0
```

![[Pasted image 20240829171123.png]]
legger til verdien (long verdi) 1 til å legges på det som er lagret i base pointer i -4.

![[Pasted image 20240829171341.png]]
cmpl - tar veriden i 9 (som er en long). og sammenliger den med -4 i base pointer veriden i -4.

jle. (jump if less then or equal). 

ALLE instruktsjoner for equality
je - jump if equal
jne -  jump if not equal
jg - jump if greater
jge - jump if greater or equal
jl - jump i less
jle - jump if less or equal
ja - jump if above
jae - jump if above or equal
jb - jump if below
jbe - jump i below or equal



dette er: (fra start)
```c
0 <= 9
```


så movl $0 to %eax register.
setter main function til å returne 0. Så main var successful

popq fjerner basepointer fra stakken. returner gmale base pointer. fjerner current functions stack frame.


# Referanse
