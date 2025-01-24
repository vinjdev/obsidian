24/08/24 11:50
Fag: [[IDATG2202]]
Tags: [[NTNU]]
___

# week 35 - computer architecture, software, CPU terminology and cache
Architectur *cpu io og memory*
![[Pasted image 20240824115445.png]]
Von neuman architectur - data and instruction *share* the same *communications* lines

Harvard architecure - *seperate communications* lines

*CPU* (a clock that generates pulses to do stuff)
- MMU - memory managment unit - each program gets its own memory area
- CU - control unit - data flow, needed for ALU to execute
- ALU - Arithmetic logic unit - executes the algoritmic or logical instructions
- Registers - the smallest and fastest storage in computer
	- lot of different registrers
	- ![[Pasted image 20240824124343.png]]
	

*Memory / ram* - random access memory - main memory, contains insteuctions and data, evrything as stored as bits (8 bits = 1 byte), bytes are loaded from memory as bytes, every address go in to memory as Bytes

*IO* - connected to computer central bus, used by CPU to handle special instructions by user. Informations gomes in and out of the computer


instructions are *different* from cpu to cpu
## Register
![[Pasted image 20240824120710.png]]
smallest is 8 bit

## ISA - instruction set architecture
each computer architecture has a specific set of instructions
different instructions set:
- ARM
- intel
- amd

Computer scientist do not care about low lever (micro architecture)
only care about
- instructions
- registers


this is assembly
![[Pasted image 20240824122355.png]]

## How the CPU works
the cpu workflow
![[Pasted image 20240824122421.png]]
IR = instructions register, laster fra listen (memory/cache/register)
IP = address to the next instructions from RAM/memory
execute instruction

*fetch, decode and execute*


### interrupts
![[Pasted image 20240824122629.png]]

When someone presses the keyboard an interrupts happen. And execute an specific piece of code. 

*Registers vs physical memory* - several program can be loaded to the RAM, but register content only has the current running program and OS.

## Program in memory
![[Pasted image 20240824124436.png]]
*text* - stores the name of the program first
*Heap* - this area grows upwards is a dynamicaly stored data
*libraies* - reusable content
*stack* - grows downwards - last item put in will always be on the top

Memory = alot of programs
CPU only works at one (i prinsippet)



# Software
## *Compiling*
abstractions level - human readable and pc readable

high level = portable
low level = unportable


GCC and assembly
![[Pasted image 20240824125136.png]]

## 32 vs 64 bit
![[Pasted image 20240824125225.png]]
the same c code but different assembly and machine code

noen ganger 32 bit raskere

## syntax
![[Pasted image 20240824125334.png]]
we need to define alot more for the machine to understand
(we only need to understand simple assembly)

Direktiver = informasjon til koden
Label = merker, start her hopp hit
Instruksjoner = kode

% = r register
$ = konstanter
() = er register i minne


instructions is called mnemonic
### examples
```bash
gcc -S -fno-asynchronous-unwind-tables asm-0.c
```
running this will generate a .s file, which is an translated .c file to assembly

parenthesis around register means we are accessing from registers
- this happens in asm-01.s

*Why learn assembly?*
![[Pasted image 20240824132208.png]]

# CPU terminology
- clock speed
- pipeline, superscalar
- machine instructions into micro operations
- out of order executions

## pipeline and superscalar
![[Pasted image 20240824142342.png]]
instructions can be divided into micro operations, which is how the cpu handles an instruction

alltid noe som fetches, decodes og executes
mye går parallet. Går ikke hele prosessen på en gang

*speculative execution* - prøver å gjette resultat


*super scalar* is to *duplicate* parts of the pipeline to process more than one instruction (thats what "b)" is in figure)

## Hyper threading/smt

![[Pasted image 20240824144324.png]]

an extension of super scalar
keeps all units of the cpu occupied, to so it can process more simultaneously 
- effecivly makes a single core act like two sepeteare logical cores

har flere cores til å regne
men kan laste FLERE programmer

## Cache
*Register* fast, regular *ram* slow
cpu has a cache is faster than ram but NOT registers

cache solves von *neuman bottleneck problem*
- cpu to fast for memory access

3 forskjellige cahce på cpu. spør hverandre.

spatial locality
temporal locality


#### write policy
write through
write back

![[Pasted image 20240824150853.png]]


![[Pasted image 20240824150904.png]]

# reviews
used to define data, orginize code and setting up the enviroment

super scalar is where the cpu duplicates a process for the cpu to run multiple instructions on the same core.
pipelining is the instruction the cpu does to execute

the c compiler takes human readibale code an compiles it for the compter to understand. regular c is high level language, easy for humans to read and program. Low level languages reguires more directives and instructions for the machine to understand.


```c
int main()
	x = 0;
	while (x <= 9) {
		x += 2
	}
	return 0;
```


# Referanse
https://www.youtube.com/watch?v=p-2aSGFvuHE&list=PLmiI5VoyQBWOMU-wMo60bT_mGgvMYnerP&index=1

compendia ch 1

