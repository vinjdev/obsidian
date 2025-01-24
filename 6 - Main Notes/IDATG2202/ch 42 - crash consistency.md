20/11/24 19:58
Fag: [[IDATG2202]]
Tags: [[NTNU]]
___
# ch 42 - crash consistency
hva skjer når strømmen går??
filsystem mellom lagres i ram

havner i en ikke konsekvent tilstand

sletting av fil:
- inode er ledig
- datablokken er ledig
- fjerner filen fra katlogen

## FSCK
file system checking - leter etter feil med filsytemet

sjekker om inodene finnes i en katalog
alle datablokker med inodene
flere sjekker med furnuftige verdier

journaling
idempotent








# Referanse
