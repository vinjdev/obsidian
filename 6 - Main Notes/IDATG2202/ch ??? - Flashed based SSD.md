08/11/24 11:58
Fag: [[IDATG2202]]
Tags: [[NTNU]]
___
# ch ??? - Flashed based SSD

ssd er bygd ppå flash
no mechanical moving parts
build on transistors like memory and processors

mye raskere

ren elektroikk, tåler mer

## storing a sinlge bit
lagrer en bit, to bit eller tre bit

jo mer bit per celler, jo kortere *levetid* 
kan kjøpe en større ssd for å kompansere

## from bits to banks / planes
flash chips er organisert i banks or planes
som har et større antall celler
![[Pasted image 20241118131252.png]]

1 page er 4 kilobyte i størrelse

## basic flash operations
hdd overskriver på samme sted som det lå noe annet

kan lese en page, kan ikke overskrive en page(kan slette da)
for å slette en hel block

må slette en block for å skrive en page i block

begresne hvor mye en celle tåler å bli slette og overskrevet
tåler 10 000 operasjoner

skriver *alltid til et nytt sted*, motsetning til hdd
- fordeler slitasje
hver gang vi skriver, så skrives så lite som mulig


![[Pasted image 20241118131952.png]]

ssd er som liten datamaskin

hvordan tar man data? hva skal en flash kontroller gjøre???

## bad approach
hvis den direkte mapper
- ikke lese av en logisk page. veldig dumt

for å overskrive en page, så slettes hele blokken

## wear leveling
![[Pasted image 20241118154426.png]]

flash control har en ledig block pool, som ny data skal inn i
og en data block pool, hvor data finnes allerede. *tomme blokker går bakerst* i ledige kø

når man sletter en fil, blir ikke slettet - blir bare ledig
blir værende til OS overskriver den

Kan overskrive med 0ere - BARE HDD, IKKE SSD (da sletter man hele blokken)

SSD har ikke kontroll over hvor blir lagret

jo større ssd, jo lengre tid for slitasje
- 512 > 256


## random vs sekvensiell
![[Pasted image 20241118155922.png]]

random accessering kan skje parallel når det skjer random
*data er spred over disken, SSD MYE KJAPPERE*

lese armer bruker for lang tid



# Referanse
