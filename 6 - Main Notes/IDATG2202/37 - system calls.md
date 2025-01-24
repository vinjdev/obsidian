09/09/24 12:38
Fag: [[IDATG2202]]
Tags: [[NTNU]]
___

# 37 - system calls

## 5
what is fork()
- makes a child process
- execute same code as parent, but with another return value(id)

process api - grensesnitt for p håndtere noen funksjoner for prosesser

getpid() får process ip
i p1.c

starter parent, så child - DETTE ER IKKE GITT
Derfor bruker vi WAIT()

opptil cpu scheduler, hvem som kommer først

wait() venter på alle barn

window har slått sammen fork() og exec(), my parametere


## 6
få kontroll over OS
- lager en liste
- allokerer memory
- laster prog inn i minne
- setter opp stack med kommando linja
- fjerner register
- kjører main
- kjører til ferdig
- så fjerner meomry fra process og process fra listen

Veldig direkte og ikke bra. Må begrense programmet til hva det har lov til å gjøre

priviligerte instrukjsoner kan bare kjøre i kernal mode
user mode kan ikke kjøre.

HVORDAN KAN VANLIG PROGRAM FÅ LOV TIL Å SKRIV TIL DISK??
- ber os om hjelp

![[Pasted image 20240910113041.png]]

kjører en og en om gangen

ENTEN kjører OS eller EN appliskajon eller en annen applikasjon

hver system call er en INTERRUPT
OS får kontroll

os kjører i kernal mode, og programet kjører i user mode. sammarbeider, så bruker program kan kjøre de priviligerte kommandoene

![[Pasted image 20240910113516.png]]
terminologi

før måtte reboot
idag bruker en timer
timer interrupt, bestemmer om os skal ta kontroll

![[Pasted image 20240910115624.png]]

dette programmet kjører printf ved hjelp av OS
- vi ser ikke printf, fordi os håndterer koden for det.








# Referanse
