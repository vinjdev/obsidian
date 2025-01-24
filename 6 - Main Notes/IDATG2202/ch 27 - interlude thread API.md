13/10/24 17:01
Fag: [[IDATG2202]]
Tags: [[NTNU]]
___

# ch 27 - interlude thread API
Shows the interface of how the os present thread creation and control


## thread creation
Pthread_create()
![[Pasted image 20241013170647.png]]
sender en funksjon peker til, returnerer en peker
og en ID

![[Pasted image 20241014121118.png]]

mere data pakker data inne i en struct

etter dette har den sin egen stack, som kjører inne i samme addresse rom som den threaden som det faktiske programmet er.
## thread completion

når en tråd er ferdig. stacken blir frigjort
![[Pasted image 20241014121815.png]]
dette blir segfault. tråder har hver sin stack, så lage LOAKL variabel i tråden vil være UTILGJENGILIG 
MÅ bruke malloc for å allokere den på heap isteadet. (da kan andre tråder bare peke til den)


## locks

når flere tråder manipulerer samme data. locks (kritisk sektor)
KAN bare ha en tråd om gangen

![[Pasted image 20241014122616.png]]
LÅS, som vi låser og unlocker.



## condition variables

en tråd sender signal(om når å kjøre osv)
sjekker en betinglese får jeg låser
![[Pasted image 20241014122826.png]]


## compiling and running

## summary

![[Pasted image 20241014123224.png]]


# Referanse
