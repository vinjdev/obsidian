01/10/24 11:07
Fag: [[IDATG2202]]
Tags: [[NTNU]]
___

# ch 20 - Paging smaller tables
page tabel are too big, take up memory

need to make page tables smaller.


HVA ER MENINGEN???????
64 bit(eller 48 som det er) ALT FOR STORT. tar for mye plass
derfor deler opp i 5 BITER. level 1,2,3,4 og offset

i level ligger VPN. VIRTUAL PAGE NUMBER (9 bits lange)
offset finner vi (DEN SPESIFIKKE TYPEN byte med data)
![[Pasted image 20241002211535.png]]
alle level peker til neste level 4 peker til 3 osv..

LEVEL 1 peker til den faktiske fysiske PAGE NUMMER I MEMORY

Hva er så offset???
Det er hvor inne i den 4kb fysiske pagen som dataen ligger
Dataen i seg selv er på den spesifikke plassen i det fysiske pagen

# HVORFOR GJØR VI DETTE??
IKKE BLAND PAGE og ADDRESSE ROM

ADDRESSE ROM er ALLE PAGENE
en adresse som dette: 0x7ffe2d2637f4
er en addresse et sted. et sted er en page

CPU jobber IKKE med virtuelle addresser. jobber helle med fysiske
CPU Må lete gjennom GIGA page table for å finne fysisk addresse

multi level hvor level bare peker til en peker til en peker.
tar aldri opp mye.


## simple solution bigger pages
example 32 bit address space
we have 2³² which is 4 gb of memory

memory is divided into 4kb pages. this is 2¹2 bytes.

jobber alltid med 4 kb pages(som regel)

page tables would be = 2³2 / 2¹2 = 2²0which is 1 million  entry is 4 bytes. so to page table size is 2²0 * 4 bytes = 4 mb

therefore we have multiple page sizes
now waste within the big  pages - *internal fragmentation*

![[Pasted image 20241001151403.png]]
sånn regner man ut størrelsen
vite hva VPN er og hva størrelsen er per page


# multi level page tables
64 bit address space kan må ha større pager. leder til intern fragmentering

ikke noe poeng å lage en page table som ikke bruker i nærheten så mye plass.

lager bare page tabel for de vi bruker.

istedet for linear page tabel. deler vi opp i flere nivårt. oversikt tabel med under tabel


Multi level page table turns linear page table into a *tree*
multi level table only allocates page table in propotion of amount of address space in use

### example
page size = 64 bytes
total memory = 16 kb
so we have (16 * 1024) / 64 => 256 pages

use 14 bit address space
1 kb = 2¹⁰
we have 16 kb memory, so -> 2¹⁴ bytes
THIS IS WAY ITS A 14 BITS ADDRESS SPACE

8 bits for VPN
we already know we have 256 PAGES so 256 = 2⁸
therefor we have 8 bit vpn

The Rest HAS TO BE 6 (offset) (the actual location)



# Referanse
