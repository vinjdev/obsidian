19/11/24 18:20
Fag: [[IDATG2202]]
Tags: [[NTNU]]
___
# ch 40 - File system implementation

vsfs - very simple filesystem

vsfs basicly lik ext4

disken blir delt i blocker på 4 kb (nesten alltid 4 kb i alle sammenhenger)

addresser dem fra 0 til 63. dette er en partition
64 blocker
![[Pasted image 20241120152422.png]]
veldig liten disk her

4kb = 2¹² 
64 = 2⁶
2¹² * 2⁶ = 2¹⁸ => 256 kb

hvor skal inneholdet av filen ligge i disken
![[Pasted image 20241120152855.png]]

første 8 blockene går til metadata
- lagres i *inoder*
- tidspunkt for filen, og rettigheter, og ID er her

hver block 4kb stor, og en Inode er 256 bytes stor
2¹²(en block) / 2⁸ => 2⁴ -> 16
*plass til 16 inoder i en block*
![[Pasted image 20241120153400.png]]
har 5 blocker reservert for inoder. 16 * 5 -> 80
MAX HA 80 filer, inkludert kataloger (en katalog er en slag fil)

enten en free list eller en bitmap
free list - linked list
bipmap - array med bits, hvor bit representerer allokert eller ledig
- bra for fragmentering

![[Pasted image 20241120153802.png]]
to bitmaps her. en for inodene og en for dataen

![[Pasted image 20241120153829.png]]
en super block
inode for filesystemet generelt


DETTE ER GRUNNEN TIL DISKEN HAR MINDRE PLASS EN DET SIES DEN HAR
- må reservere plass til inodene og bitmap
- holde datastrukterene

#### hvordan er metadata koblet til filen og data
![[Pasted image 20241120155750.png]]
i en inode ligger det 15 addresser
hvis man har større filer, har man ikke plass til alle addressene

må derfor LÅNE en datablock, til lagre flere adresser
- peker til den -> single indirect addresering

dette eksemplet er med 16kb blokker og 64b blokk adresser

med denne metoden kan man lagre filer intil 32 mb

*2¹¹ er antall addresser man har plass til per blokk.*

ext4 funker sånn
- små filer er direkte addresert til inoden.
- litt størrefiler, peker til andre datablockker som holder direkte addresser
- osv, osv

12 FØRSTE er direkte addresering
3 siste er for multi level index

de tre siste adressene i en inode brukes til dette
- singel
- dobbel
- trippel

filer er vanligvis små
noen kan være veldig store
er veldig mange filer


## eksempel
blokkstørrelser kan være alt mulig

endianness - beskriver rekkefølgen for en sekvens med bytes er lagret i computer memory







# Referanse
