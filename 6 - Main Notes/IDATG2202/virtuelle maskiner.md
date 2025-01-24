22/11/24 14:08
Fag: [[IDATG2202]]
Tags: [[NTNU]]
___
# virtuelle maskiner
![[Pasted image 20241122140836.png]]

virtuelle maskiner har sitt eget operativ system

docker deler operativsystem

UNIKERNAL

## hva er virtuell maskiner
en singel computer hoster flere virtuelle maskiner


hvorfor virtuallisere?
- isolere tjenester
- sparer strøm og plass
- lettere å vedlikeholde


## krav
hardware som tillater det

sensitiv instruksjon - kan bare kjøre i kernal mode

x86 hadde før 17 instruction som ikke var mulig uten kernel mode.

## hypervisors
mellom lag mellom fysiske maskinvaren og de virtuelle maskinene
hypervisor byttet ut funksjon som ikke kan gjøres

all koden må sjekkes av hypervisor. i tilfelle ikke har tillatelse til å kjøre

Binary translation
- hyprvisor sjekker gjenmnom instruksjoner av gjeste OS
- ser etter hopp

enten kjører hyprvisor eller kjøere main os, eller kjører gjeste os
![[Pasted image 20241122153622.png]]

## paravirtualisering
samme som binary translation, men ikke under execution
endrer source code for OS på forhånd

reduserer antalll overganger til VMM

## memory

page faults
- tar lang tid

![[Pasted image 20241122155247.png]]
viser minnehåndtering med virtuell addresse rom og fysisk addresse

problemet her:
- i en virtuell maskin
![[Pasted image 20241122155330.png]]
slår opp i en gjeste page tabel.
tror dette er ekte ram. Men det blir mappet til hypervisor 
- til EKTE page tabel
- som igjen går til EKTE RAM

TO nivåer

MMU har TLB cache
- addresse fra prosessen til ram på maskinen

man må ha en egen peker fra *VIRTUELL RAM TIL FYSISK PLASS I RAM*
- tredje page tabell
![[Pasted image 20241122155810.png]]

fyller tlb utifra den

minnehåndtering blir ytelse problem

HARDWARE MÅ HA virtuell mangament støtte for minne

idag skjønner MMU om at virtuell maskiner finnes


fortsatt problem
på tlb miss. Må gjøre page walk
4 page tabel. ALLE er virtuelle (i vm og i virtuelt for minne), må oversette 4 ganger

kan ende opp med 24 oversettelser for en simpel page walk


## vm wares
noen virtuell maskiner kan skur av støtte for minne

noen er bedre på ting enn andre

operasjoner? IO? trenger mye kernal mode? trenger minne?







# Referanse
