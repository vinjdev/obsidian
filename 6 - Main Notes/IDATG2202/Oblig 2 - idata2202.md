27/09/24 09:00
Fag: [[IDATG2202]]
Tags: [[NTNU]]
___

# Oblig 2 - idata2202

[[oblig 2 tegning]]

# 1 address translation
FINNE INDEX FOR PAGE TABLE

1. kjører den gir 4096
får størrelsen på en page i memory i BYTES. 
Det vil si den er 4kb

virtual address has two parts
VPN - index (den som ligger i level 1 som vi skal ha)
offset - exact location within physical page

64 bit addresse
pagesize = 4096 bytes

4096 = 2¹² => 12 bit offset
splitter resten inn i 4 Level
bruker ALDRI 64 bits heller 48
48 - 12 = 36
alle 4 leveler har 9 bits hver.

0x7ffe2d2637f4
in binary
011111111111111000101101001001100011011111110100
read the 9 last bits before offset(12 bits)
![[Pasted image 20241002215906.png]]
VPN = 99
siste level (level 1) 

index til page table som har den fysiske page nummeret i minne.
bruker offset sammen med addressen ti å finne data

# 2 cache behavior
Hvor mange bytes er arrayen, når random trekk blir TREGER enn sekvensiell trekk

spørsmål er: har den plass på cache line???


l1 128 kb
l2 1mb
l3 6mb

første 4000 * 4 bytes = 16kb - passer i l1 eller l2

40000 * 4 bytes 160 kb - passer fint i l2

400000 * 4 bytes = 1,6 mb - litt tregere her


- Blir 0.3 sekunder her -
4 000 000 = 16 mb MYE TREGERE FRA HER

40 000 000 * 4 bytes = 160 mb

400 000 000 * 4 bytes = 1,6 gb

MERE cache MISSES. tvinger cpu til hente data fra memory. 

sekvensiell access = loader opp en cache line. så neste element er neste i cache line. spatial locality
verdien som er nærme er stor sjans for at ble hentet neste gang


WHY cache miss in random access.
random_index has data spread around in memory. random access hit in different location in memory

cache miss skjer fordi - data i minne langt fra hverandre. spatial locality ikke opprettholdt

# 3
VIRT = 3568
RES = 1276

virt er totale virtuelle minnne som blir brukt
res er del av prosessen som blir brukt i det fysiske minne

så mem1 tar ikke noe res, annet en de libsa som brukes
mem2 gjør akkurat det samme bare med array init som blir lagt i den fysiske rammen

malloc er virtuall only


VIRT = 3568
RES = 2296

2296 - 1276 = 1020 kb

size = er akkurat en kilobyte
(262144 * 4) / 1024 = 1024  

ET HELT TOMT PROGRAM:
![[Pasted image 20241008125526.png]]
1 mb mindre i virt, siden fjerna malloc
# Referanse
https://gitlab.com/erikhje/iikos/-/blob/master/oblig/2024-2.md