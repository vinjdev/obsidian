12/10/24 10:02
Fag: [[IDATG2202]]
Tags: [[NTNU]]
___

# ch 26 - intro concurrency

*CONCURRENCY = SAMTIDIGHET*

tråder = lettvekts prosesser
tråder *deler* adresse rommet til en prosess

hver tråd har sin egen instruksjons peker
ikke BARE context switch mellom processer, men også tråder

HVA er tråd og hva er prosess
hver tråd har sin egen: register, instruksjon peker stack og base peker

HVER TRÅD HAR HVER SIN STACK(som bildet), ellers deler


a single runninng process = thread
multi threaded has more than on point of execution

single threaded address space
![[Pasted image 20241013115325.png]]

## thread creation
example:
program makes two threads - each do individual work
thread creation almost like function call. each thread takes in a different paramter

alle vi har laget program er en tråd programmer

enklere raksere å skifte mellom tråder(bruker samme adresse rom)
ungår at en process blocker på IO.
kan ha en tråd som henter data, mens en annen SOM FORTSATT LYTTER.


Årsaker til TRÅDER
*PARALELLISERING OG BLOKKERING PÅ IO*

prosesser konkurrer, mens tråder sammarbeider

prosess er beskytte ved forsjellige addresse rom, mens tråder ligger på samme og deler.

![[Pasted image 20241013161814.png]]
tre tråder som kjører
OS scheduler bestemmer hva som kommer først
NULL kontroll over dette



## why it get worse: shared data
when two thread updates a shared global variable
computer not always produces *deterministic* results

OSstep code thread intro
![[Pasted image 20241013162056.png]]
deler global variable array
![[Pasted image 20241013162226.png]]

går fint med korte arrays
race condition i code, som gjør det vansklig. Kan bli ikke determinitisk
- EN THREAD IKKE rekker å ikrementere verdi før en annen process har startet. så sender til memory en LAVERE verdi, en det den neste tror det er på

## the heart of the problem uncontrolled scheduling

## The wish for atomicity 
![[Pasted image 20241013165842.png]]


## one more problem waiting for another

## summary




# Referanse
