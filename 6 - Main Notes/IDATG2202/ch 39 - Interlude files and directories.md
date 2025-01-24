18/11/24 21:47
Fag: [[IDATG2202]]
Tags: [[NTNU]]
___
# ch 39 - Interlude files and directories

hvordan tar vi vare på data, selv når strømmen er slått av

fil er en abstrksjon

ls -li (i gir iden til filen lav nivå)

## creating files
open()
lager en ny fil
![[Pasted image 20241119155723.png]]

*open* returnerer en *file descriptor*
- er bare en INT, en id for filen

![[Pasted image 20241119171945.png]]
måten man lager en midlertidig fil

mktemp lager en fil med unik id


hvorfor returnerer open *fil deskriptor 3*????

0,1 og 2. finnes fra før
0 = standard input
1 = standard input
2 = standard error

alle proceeser har allerede 3 filer oppe, derfor er disse brukt

## eksempel

```bash
cat | wc
hei
til deg
```

![[Pasted image 20241119172547.png]]

her ser man hvordan de to programmene bruker fil deskriptorene 0 og 1 og 2

wc blir omdirigert til å lese fra pipen

## writing immediatiely with fsync()

skrive det som er mellomlagret på ram til disk

![[Pasted image 20241119173605.png]]
samme som før bare med fsynch

fysync = sikkerhetes funksjon, sikrer at det som ligger i ram faktisk blir lagret på disk

må skje på filen og katalogen


mv gir filen nytt navn
- atomisk operasjon (skjer uavbrutt)

dette er måten vim eller emcas håndterer det å lage filer:
![[Pasted image 20241119175152.png]]
temp fil, så overfører til fra ram til disk, deretter renamer filen(som er en atomisk operasjon)

## informasjon om filer
metadata
gjemt informasjon om filer

stat()
fstat()

![[Pasted image 20241119175352.png]]

gir all data om filen
Inode og links viktige her

## sletting av fil
rm 
bruker unlink

forstå kataloger
![[Pasted image 20241119175910.png]]

rm (sletter fil)
rm -rf (sletter alt)

katalog er osgå bar en fil
![[Pasted image 20241119180901.png]]
bryr oss bare om filnavn og inode nr


hvorfor heter det unlink

unlink fjerner filen fra en katalog
hardlink er oppføring av fil i en katalog

kan lage en symbolsk link mellom filer
kan bruke sym og hard
hard link vil bli samme fil med samme inode nummer


## mkfs

linux bruker .ext4
mounter det med mount funksjon til disk

det som skjer med å bygge arch
formaterer filsystemet og mounter det til disk



# Referanse
