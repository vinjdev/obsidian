16/10/24 12:17
Fag: [[IDATG2202]]
Tags: [[NTNU]]
___

# ch 30 - Condition variables
process = program under utførelse.
program = noe på disk
program laster på memory
CPU leser instruksjoner i program, og starter process

alle programmer som kjører er: *en* tråd programmer

fork = ny page table med sin egen tråd, en tråd

p thread create = flere tråder på samme page table


main tråd går inn SÅ går child.
vi må styre rekkefølge

![[Pasted image 20241016122336.png]]
simpelt program som starter en child process

spin waiting IKKE BRA, ikke bra å kjøre å teste hele tiden

## definitions and routines
![[Pasted image 20241016122535.png]]
unngår spin waiting


*producer consumer*
produser tråder tar noe inn og consumer tar ut


*semorf* - signal
- kontrollerer når en tråd skal kjøre eller vente
- unngår at tråder tilgang på ressureser samtidig



# barrier java atomicint
java har muligheten til å isolere en trå til å kjøre om gangen
- bruk av synchronized

java er bedre enn C. for dette

C har noe i c17
![[Pasted image 20241025174547.png]]

kan bruke med c17 og denne liben
![[Pasted image 20241025174609.png]]



# Referanse
