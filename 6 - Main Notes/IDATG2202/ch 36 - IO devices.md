25/10/24 17:55
Fag: [[IDATG2202]]
Tags: [[NTNU]]
___
# ch 36 - IO devices
persistence = standhaftighet

whats a program? cant be a program without output. (whats the purpose of it running) input should be required.
- what are general mechanisms and what makes them efficient


![[Pasted image 20241105112512.png]]

![[Pasted image 20241105112537.png]]
keyboard og mus. de trege *IO ENHET*

IO ENHET = en liten datamaskin

hvordan kontrollerr vi en io-enhet
CPU sender data til registere, viser en API som enhetene leser fra
- IO har status register

![[Pasted image 20241105191101.png]]

Istedet for å vente på IO skal bli ferdig. Kjører context switch
- gi fra cpu så en annen prosess
#### More efficient data movement with DMA
- DMA - direct memory access
cpu må flytte data til disk, så disk kan ta over.

DMA egen datamaskin som får jobben om å håndtere data overføring

![[Pasted image 20241107174119.png]]

![[Pasted image 20241107174135.png]]

Memory mapped I/O


The Device driver
![[Pasted image 20241107221636.png]]

All kompleksitet blir lagt bak en abstraksjon






# Referanse
