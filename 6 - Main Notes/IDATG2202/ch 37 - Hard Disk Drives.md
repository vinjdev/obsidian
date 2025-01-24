08/11/24 09:55
Fag: [[IDATG2202]]
Tags: [[NTNU]]
___
# ch 37 - Hard Disk Drives

How is data actually laid out and accessed?

## interface

512 byte blocks
fra 0 og oppover (n-1)
som er *addresse rommet* for disken (address space)


## Basic geometry
*Platter* - circular surface
*spindle* - spins the platter (like a motor)
*RPM* (rotation per minute) - 7200 - 15000 a single rotation takes 6 ms

## a Simple disk drive
![[Pasted image 20241108112135.png]]
veldig tett lagring(som hår) på de magnetiske platene

![[Pasted image 20241108113756.png]]
spor blir lest med lese arm, som flyttes ut i fra hva som skal leses

liten forskyvelse, så når man leser 24 etter 23
![[Pasted image 20241108114002.png]]

## I/O time: doing the math
hvor lang tid tar det å flytte armen til siden
flytte platen til riktig sted
hvor lang tid tar det å lese av data

HDD like rask som SSD - i lese av data
- mekaniske deler tar for lang tid

![[Pasted image 20241108115154.png]]

size per track = 1 mb
7200 / 60 = 8.3 ms (rotation time)
- denne skal deles på to trenger bare å rotere en halv gang
average seek time (må vite) = 5 ms
block size = 4kb 
transfer = (block size / size per track) * rotation time

![[Pasted image 20241108115622.png]]
SÅ langt tid å hente data

MYE raskere å lese data sekvensielt



# Referanse
