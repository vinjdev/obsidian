18/11/24 16:40
Fag: [[IDATG2202]]
Tags: [[NTNU]]
___
# RAID
redundant array of independent disks


er en måte å kombinere disker så det ser ut som en

## raid 0
![[Pasted image 20241118195356.png]]

to disker blir kombinert til en DISK
block 1 er på 0, block 2 er på 1,block 3 er på 0 OSV....

hvis en av diskene ryker, mister man all data

bra for masse filer, som må kunne leveres raskest mulig
INGEN SKRIVING, BARE LESING


## raid 1
![[Pasted image 20241118200708.png]]
raid 1 er speiling av data lagring
lagrer data DOBBELT
vanlig i *SERVERE*

## raid 5
![[Pasted image 20241118200834.png]]

går utover ytelse ved store disker

## Paritet
kan brukes til å regne ut hva en hel disk var før den ble ødelagt
![[Pasted image 20241118203126.png]]
hvis den i midten ble ødelagt, skjønner man hva den var ved hjelp av paritet

LAGRES IKKE PÅ EN DISK. SPRER UTOVER
se. derfor man ser p på noen

HVIS en disk ryker, er man sårbar
- skjer det igjen. mister man alt (ingen paritet)


## JBOD
just a bunch of disk
den som brukes i skyhigh
![[Pasted image 20241118205611.png]]

# IOPS
input output operation per second

hvor mange 4k operasjoner kan man gjøre per sekund
![[Pasted image 20241118213418.png]]




# Referanse
