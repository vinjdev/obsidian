14/10/24 12:33
Fag: [[IDATG2202]]
Tags: [[NTNU]]
___

# ch 28 - locks

en eller annen global variabel, kan ikke manipuleres av flere tråder samtidig, må ha en lås

mutex = mutial exclusion
when one is in CRITICAL zone it EXCLUDE the other one

mutex er en flag som sier at koden mellom er låst.

![[Pasted image 20241014130232.png]]
andre tråder vil skippe denne koden

hvordan kan OS gi en sånn lås.
siden globale variabler som øker med en verdi, kan ha en interupt mellom alle instruksjoner.


- lukke ut andre tråder
- rettferdig - la andre tråder kan få kjøre
- god ytelse
### building a lock


### controlling interrupts
![[Pasted image 20241016115425.png]]

skrur av og på interrupts

virker ikke på flere cpu kjerner


bruk heller et flag
![[Pasted image 20241016115518.png]]
lock vil alltid sjekke helt til flag = 1

dette gjøres atomisk operasjon


LÅSER TILGANG, VIL påvirke ytelse

## ATOMISK OPERASJON:
*en operasjon som kan utføres uten at den blir avbrutt*
vis ikke, INGENTING BLIR UTFØRT

for at tråder skal kunne modifisere delte ressurser trygt




# DEADLOCK
et set med tråder/prosess venter på en av dem skal bli ferdig.
bare *en* kan fikse dette.

*alle venter*

![[Pasted image 20241016121512.png]]
må låse i stigende rekkefølge



# Referanse
