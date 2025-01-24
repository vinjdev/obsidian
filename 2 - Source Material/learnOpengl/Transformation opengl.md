29/07/24 14:22
Tags: [[OpenGL]]
___

# Transformation opengl
## Vectors
Vektorer er retninger og posisjoner.
vanlige matematiske regler gjelder for disse.
- addisjon, subtraksjon er veldig lett
- skalar gjelder for alle elementer
lengen av en vektor er hyptenusen av x og y retningen
![[Pasted image 20240822155139.png]]
## Vector multiplikasjon
det å gange to vektorer har ingen bestemt definisjon. Men det er dot produkt og kryss produkt, man får hvis man skal gjøre dette

#### *Dot product*
![[Pasted image 20240807174312.png]]

Regner ut hva skalaren er mellom v og k
![[Pasted image 20240807174935.png]]
her blir den -0.8
får å så finne hva vinkelen er:
*Tar invers cos av skalar*

#### Kryss produkt
har to uparallelle vektorer og lager en tredje som står i z akse ut fra de to andre.
![[Pasted image 20240807175254.png]]

![[Pasted image 20240807175333.png]]
sånn regnes det ut

## Matriser
er en liste med elementer
står i (i,j) format. i er rekker j er kolonner
(det er det motsatte av x,y grafer), (i går ned og j går til siden)

addisjon og subtraksjon av samme størrelse matrise -> er bare rett fram - eller +

skalar er det samme

#### multiplikasjon
er litt anderledes enn vanlig
1. kan bare gange HVIS kolonner på venste matrise = rekker på høyre matrise
2. matrise A * B vil *ikke* gi samme svar som B * A
man ganer kolonne(1. matrise) med rekke(2. matrise)
![[Pasted image 20240807180256.png]]




# Referanse
https://learnopengl.com/Getting-started/Transformations
